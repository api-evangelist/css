# CSS (Cascading Style Sheets)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Cascading Style Sheets (CSS) is a W3C web standard for describing the presentation of documents written in HTML and XML, including layout, colors, typography, and animations. CSS is a foundational web technology maintained by the W3C CSS Working Group and implemented natively by every major web browser. The CSS Object Model (CSSOM) and CSS Houdini extensibility APIs expose CSS to JavaScript at runtime.

**APIs.yml URL:** https://raw.githubusercontent.com/api-evangelist/css/refs/heads/main/apis.yml

## Scope

- **Type:** Standard
- **x-type:** standard
- **Body:** W3C CSS Working Group

## Tags

CSS, Web Standards, W3C, Styling, Browser

## Standards Surface

CSS does not have a single REST API. It is a collection of W3C specifications implemented by browser engines. The most relevant programmatic surfaces for developers are:

- **CSSOM (CSS Object Model)** - JavaScript access to stylesheets and computed styles via DOM APIs.
- **CSS Houdini** - Low-level extensibility APIs including Paint, Layout, Animation Worklet, and Properties and Values.

## Key Specifications

- CSS Cascading and Inheritance Level 3
- Selectors Level 3 / 4
- CSS Color Levels 3-5
- CSS Fonts Levels 3-4
- CSS Flexible Box Layout (Flexbox) Level 1
- CSS Grid Layout Level 1
- Media Queries Levels 3-4
- CSS Containment Level 1
- CSS Writing Modes Level 3
- CSS Box Model Level 3

A complete and up-to-date list is at https://www.w3.org/Style/CSS/current-work .

## Features

- Cascade, specificity, and inheritance
- Powerful selectors (structural, attribute, pseudo-class, pseudo-element)
- Box model and modern layout (Flexbox, Grid, Subgrid)
- Responsive design via Media Queries
- Color, gradients, and rich typography
- Animations and transitions
- CSSOM access from JavaScript
- CSS Houdini for custom paint, layout, and properties

## Use Cases

- Web page styling
- Responsive and adaptive UI
- Component libraries and design systems
- Pure-CSS web animations
- Browser polyfills via Houdini worklets
- Accessibility-aware presentation

## Resources

- W3C CSS Home: https://www.w3.org/Style/CSS/
- CSS Specifications: https://www.w3.org/TR/?tag=css
- CSS Current Work: https://www.w3.org/Style/CSS/current-work
- CSS Working Group: https://www.w3.org/groups/wg/css/
- CSSWG Drafts (GitHub): https://github.com/w3c/csswg-drafts
- CSS Houdini Drafts (GitHub): https://github.com/w3c/css-houdini-drafts
- MDN CSS Reference: https://developer.mozilla.org/en-US/docs/Web/CSS

## Maintainers

- Kin Lane (kin@apievangelist.com)
