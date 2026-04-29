# CSS (Cascading Style Sheets)

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
