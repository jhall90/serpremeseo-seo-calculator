Here is the updated documentation, formatted exactly like your previous version with the consistent use of horizontal rules, bolded callouts, and clean code blocks.

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

- Drop-in custom element (`<seo-calculator>`)
- Works in WordPress, Webflow, Wix, Squarespace, Shopify, or plain HTML
- No dependencies required
- Loadable via CDN for simple integration
- Shadow DOM isolation for predictable styling
- Supports multiple **branding modes** for agencies, publishers, and embeds
- Emits **custom events** for analytics and conversion tracking

---

## CDN Usage (jsDelivr)

After pushing updates to this repository, the calculator may be loaded via CDN.

```html
<script src="https://cdn.jsdelivr.net/gh/jhall90/serpremeseo-seo-calculator@latest/dist/seo-calculator.min.js"></script>

<seo-calculator theme="system"></seo-calculator>
```

Place the script **before** using the `<seo-calculator>` element.

---

## Basic Usage Example

Include the script, then place the custom element anywhere in the document:

```html
<script src="https://cdn.jsdelivr.net/gh/jhall90/serpremeseo-seo-calculator@latest/dist/seo-calculator.min.js"></script>

<body>
    <seo-calculator theme="system"></seo-calculator>
</body>
```

This will render the calculator using its default UI and any active CSS variables available on the page.

---

## Branding Modes

The calculator supports controlled branding presets depending on your use case.

| Branding Mode | Intended Use Case                | Behavior                                 |
| :------------ | :------------------------------- | :--------------------------------------- |
| `brand`       | Agency sites / owned properties  | Full branding and visual overrides       |
| `minimal`     | Blogs / educational resources    | Limited branding and neutral visuals     |
| `off`         | Neutral publishers / comparisons | No branding overrides and no attribution |

**Example:**

```html
<seo-calculator
    branding="minimal"
    theme="system"></seo-calculator>
```

---

## Events (Analytics & Conversion Tracking)

The calculator emits events that you can listen to for analytics, lead scoring, or “intent” tracking.

### seo-calculator:ready

Fires once after the calculator initializes.

```javascript
document.addEventListener("seo-calculator:ready", (e) => {
    console.log("Calculator ready:", e.detail);
    // Access e.detail.branding, e.detail.theme, e.detail.version
});
```

### seo-calculator:update

Fires when meaningful calculator inputs change (deduped internally).

```javascript
document.addEventListener("seo-calculator:update", (e) => {
    console.log("Calculator updated:", e.detail);

    // Example: capture totals
    const monthly = e.detail?.totals?.monthly;
    const oneTime = e.detail?.totals?.oneTime;

    // Send this into your analytics stack (GA4, Meta Pixel, etc.)
});
```

---

## Advanced Styling (Custom Branding)

The calculator is styled using CSS Variables. You can pass your brand colors directly into the `style` attribute.

### Standard Manual Branding

| Variable                | Description                                    |
| :---------------------- | :--------------------------------------------- |
| `theme`                 | Use 'system' unless forcing light or dark mode |
| `--brand-top`           | Gradient start color for brand elements        |
| `--brand-bottom`        | Gradient end color for brand elements          |
| `--chart-onpage`        | Color used for On-Page SEO data segments       |
| `--chart-tech`          | Color used for Technical SEO data segments     |
| `--chart-offpage`       | Color used for Off-Page SEO data segments      |
| `--chart-reporting`     | Color used for Reporting data segments         |
| `--bg-light`            | Main background color in Light Mode            |
| `--panel-light`         | Inner card background in Light Mode            |
| `--text-light`          | Text color in Light Mode                       |
| `--bg-dark`             | Main background color in Dark Mode             |
| `--panel-dark`          | Inner card background in Dark Mode             |
| `--text-dark`           | Text color in Dark Mode                        |
| `--font-family`         | Typographic family used across the UI          |
| `--ui-option-font-size` | Font size for dropdowns and inputs             |

```html
<seo-calculator
    branding="brand"
    theme="light"
    style="
        --brand-top: #013740;
        --brand-bottom: #2B5C64;
        --chart-onpage: #D8724E;
        --chart-tech: #DFA07F;
        --chart-offpage: #B5C4C9;
        --chart-reporting: #94A3B8;
        --font-family: 'Lato', sans-serif;
    "></seo-calculator>
```

---

## Elementor (WordPress) Integration because I personally like them. Not Sponsored.

Use this configuration to automatically sync the calculator with your Elementor Site Settings:

```html
<seo-calculator
    branding="brand"
    theme="system"
    style="
        /* -----------------------------------------------------------
           ELEMENTOR GLOBAL VARIABLE REFERENCE (Site-Wide)
        ----------------------------------------------------------- */

        /* BRAND COLORS */
        --brand-top: var(--e-global-color-primary);
        --brand-bottom: var(--e-global-color-secondary);

        /* CHART COLORS */
        --chart-onpage: #D8724E;
        --chart-tech: #DFA07F;
        --chart-offpage: #B5C4C9;
        --chart-reporting: #94A3B8;

        /* UI - LIGHT THEME */
        --bg-light: #F9F9F9;
        --panel-light: #FFFFFF;
        --text-light: var(--e-global-color-text);

        /* UI - DARK THEME */
        --bg-dark: #013740;
        --panel-dark: #2B5C64;
        --text-dark: #F9F9F9;

        /* FONT & SIZE */
        --font-family: var(--e-global-typography-text-font-family, inherit);
        --ui-option-font-size: 13.3333px;
    "></seo-calculator>
```

---

## Neutral Publisher Embed (Branding Off)

If you are a publisher or want a neutral embed (no branding or attribution), use:

```html
<seo-calculator
    branding="off"
    theme="system"></seo-calculator>
```

---

## Private Source Code

This repository contains **only the distributable build**.
The following items are intentionally excluded:

- Source JavaScript
- Development files
- Build pipeline
- Testing utilities

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
https://cdn.jsdelivr.net/gh/jhall90/serpremeseo-seo-calculator@v1.0.0/dist/seo-calculator.min.js
```

---

## Repository Structure

```
/
├── dist/
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
