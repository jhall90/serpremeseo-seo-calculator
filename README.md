# SERPremeSEO SEO Calculator (For Public Distribution)

A lightweight, framework-agnostic SEO Pricing Calculator delivered as a Web Component.

This repository contains only the **compiled, production-ready distribution** of the calculator for embedding on websites, CMS platforms, and client implementations.

The full source code, build system, and development workflow are maintained in a **separate private repository**.

---

## Live Demo (GitHub Pages)

Fully interactive demo:

https://jhall90.github.io/serpremeseo-seo-calculator/

---

## Features

-   Drop-in custom element (`<seo-calculator>`)
-   Works in WordPress, Webflow, Wix, Squarespace, Shopify, or plain HTML
-   No dependencies required
-   Supports automatic branding when paired with the SERPremeSEO Brand Loader
-   Loadable via CDN for simple integration
-   Shadow DOM isolation for predictable styling

---

## CDN Usage (jsDelivr)

After pushing updates to this repository, the calculator may be loaded via CDN.

```html
<script src="https://cdn.jsdelivr.net/gh/jhall90/serpremeseo-seo-calculator@latest/dist/seo-calculator.min.js"></script>

<seo-calculator></seo-calculator>
```

Place the script **before** using the `<seo-calculator>` element.

---

## Basic Usage Example

Include the script, then place the custom element anywhere in the document:

```html
<script src="https://cdn.jsdelivr.net/gh/jhall90/serpremeseo-seo-calculator-public/dist/seo-calculator.min.js"></script>

<body>
    <seo-calculator></seo-calculator>
</body>
```

This will render the calculator using its default UI and any active CSS variables available on the page.

---

## Optional: Brand Loader Integration

For automatic brand-color theming, include the SERPremeSEO Brand Loader **before** the calculator:

```html
<script src="https://cdn.jsdelivr.net/gh/jhall90/serpremeseo-brand-loader/dist/brand-loader.min.js"></script>
<script src="https://cdn.jsdelivr.net/gh/jhall90/serpremeseo-seo-calculator-public/dist/seo-calculator.min.js"></script>

<seo-calculator></seo-calculator>
```

This enables the calculator to inherit:

-   `--brand-top`
-   `--brand-bottom`
-   `--chart-onpage`
-   `--chart-tech`
-   `--chart-offpage`
-   Light/Dark backgrounds
-   Typography variables

---

## Private Source Code

This repository contains **only the distributable build**.
The following items are intentionally excluded:

-   Source JavaScript
-   Development files
-   Build pipeline
-   Testing utilities

To request access, report issues, or inquire about collaboration, contact the repository owner.

---

## Versioning & CDN Releases

Tag a release:

```sh
git tag v1.0.0
git push origin v1.0.0
```

Load a specific version via CDN:

```
https://cdn.jsdelivr.net/gh/jhall90/serpremeseo-seo-calculator-public@v1.0.0/dist/seo-calculator.min.js
```

---

## Repository Structure

```
/
├── dist/
│   ├── seo-calculator.js
│   └── seo-calculator.min.js
│
├── demo/
│   └── index.html
│
├── LICENSE
└── README.md
```

---

## License

Distributed under the MIT License.  
See the LICENSE file for details.
