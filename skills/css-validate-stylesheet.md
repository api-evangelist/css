---
name: css-validate-stylesheet
description: >-
  Validate a stylesheet or a page's CSS against a chosen CSS profile using the W3C CSS
  Validation Service, and read the result correctly — including the trap that an invalid
  stylesheet comes back as HTTP 200.
api: W3C CSS Validation Service
generated: '2026-09-07'
method: generated
source: >-
  https://jigsaw.w3.org/css-validator/manual.html#requestformat,
  https://jigsaw.w3.org/css-validator/api.html and wsdl/css-validator.wsdl
operations:
  - validateURI
  - validateText
base_url: https://jigsaw.w3.org/css-validator/validator
auth: none
---

# Validate CSS with the W3C CSS Validation Service

The service is anonymous — no key, no account, no header. Both operations are declared
`wsdlx:safe="true"` in the W3C-published WSDL, so they are pure reads and a retry is always
free.

## Choose the operation

Both are the same endpoint; the parameter you send picks the operation.

| Operation | Parameter | Validates |
|---|---|---|
| `validateURI` | `uri=<url>` | A document at a URL. HTML or CSS. `@import` is followed. |
| `validateText` | `text=<css>` | An inline CSS fragment. CSS only. |

Send exactly one of `uri` or `text`. Sending neither is the `invalidDataFault` case.

## Build the request

Plain HTTP GET against `https://jigsaw.w3.org/css-validator/validator`.

```
GET /css-validator/validator?text=a%7Bcolor%3Ared%7D&output=json&profile=css3
Host: jigsaw.w3.org
```

Parameters, with the defaults the service applies when you omit them:

- `profile` — `css1`, `css2`, `css21`, `css3`, `svg`, `svgbasic`, `svgtiny`, `mobile`,
  `atsc-tv`, `tv`, `none`. Defaults to `css2`. **Set this explicitly.** The default is CSS 2,
  which will report modern CSS as invalid.
- `output` — `html` (default), `xhtml`, `soap12`, `text`, or `json`. Use `json` or `soap12`
  for machine reading. `json` is not in the manual's parameter table but is served; `soap12`
  is the format the WSDL describes.
- `usermedium` — the `@media` context. Defaults to `all`.
- `warning` — `no`, `0`, `1`, `2`. Defaults to `2`.
- `lang` — message language. Defaults to `en`.

## Read the result — the important part

**An invalid stylesheet returns HTTP 200.** Validity lives in the body, not the status line.

```json
{ "cssvalidation": {
    "uri": "file://localhost/TextArea",
    "checkedby": "http://www.w3.org/2005/07/css-validator",
    "csslevel": "css3",
    "validity": true,
    "result": { "errorcount": 0, "warningcount": 0 }
} }
```

1. Check `validity` (boolean). That is the pass/fail.
2. Read `result.errorcount`. Errors are specification violations.
3. Read `result.warningcount` separately. **Warnings never make a document invalid** — they
   flag things that may behave oddly in some user agents. Do not fail a build on them unless
   that is a deliberate policy choice.
4. In the `soap12` output, errors arrive grouped by source stylesheet: `result.errors.errorlist`
   repeats, once per stylesheet reached through `@import` or a `<link>`. Each `error` carries
   `line`, `errortype`, and optionally `context`, `message`, `property`, `errorsubtype` and
   `skippedstring`.

Treating a validation error as a call failure and retrying is the single most common mistake
against this API — the call already succeeded.

## Faults, as distinct from findings

- `invalidDataFault` (`soap:Sender`) — your request was wrong: neither `uri` nor `text`, or a
  parameter outside the documented set. Fix the request; do not retry it unchanged.
- `processingFault` (`soap:Receiver`) — the validator failed. Retry once, after the interval
  below.

## Rate limit

W3C publishes one rule and it is on you to honor it: **sleep at least one second between
requests** when validating a batch. There are no `RateLimit-*` headers and no `Retry-After` —
nothing at runtime will tell you that you are going too fast.

If you need volume, stop calling the public service. Download the jar and run
`java -jar css-validator.jar <url>` locally. Note that the hosted service runs a stable
release that is generally older than the source, so local and hosted results can differ.

## What this skill cannot do

Nothing here writes, so nothing here needs reversing, an idempotency key, or a dry run — the
whole service is already a no-effect check.
