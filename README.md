# AI-Co-Piloted Typographic Card

A responsive and accessible article card created for the **AI-Co-Piloted Typographic Card** lab.

## Live Website

After enabling GitHub Pages, the expected URL is:

`https://blen-hadgu-web.github.io/ai-typographic-card/`

## Public Repository

`https://github.com/blen-hadgu-web/ai-typographic-card`

## Project Overview

The card contains all required content:

- A local SVG image
- A category badge
- A fluid headline
- A short description
- A “Read Article” button
- A user-controlled dark-mode switch

## Project Structure

```text
ai-typographic-card/
├── .nojekyll
├── card-illustration.svg
├── favicon.svg
├── index.html
├── README.md
├── TESTING-CHECKLIST.md
└── styles.css
```

## Run Locally

No package manager, framework, build command, or JavaScript is required.

1. Download or clone this repository.
2. Open `index.html` in a modern browser.

A local development server such as VS Code Live Server may also be used.

## AI Tool and Prompt

**AI tool:** ChatGPT

### Generation prompt

> Act as a senior frontend engineer. Create a semantic, responsive Profile or Article Card using one HTML file and one CSS file. The card must contain an image, category badge, headline, short description, and a “Read Article” button.
>
> Build the CSS architecture with low-specificity class selectors, cascade layers, and custom properties declared on `:root`. Do not use `!important`.
>
> Use `oklch()` for every background, text, border, focus, shadow, and accent color. Include a working, accessible dark-mode toggle.
>
> Use only relative sizing units such as `rem`, `em`, `%`, viewport units, and container-query units. Do not use `px` for typography, spacing, borders, or layout dimensions.
>
> Create a headline token with `clamp()` that has a clear minimum, fluid middle expression combining `rem` and `vw`, and maximum. Use `text-box: trim-both cap alphabetic` on the category badge and button. Because `text-box` is cutting-edge, provide a line-height and padding fallback and apply `text-box` inside `@supports`.
>
> Use CSS Grid or Flexbox, a container query for the card layout, semantic HTML, accessible image alternative text, visible keyboard focus, and reduced-motion support.

## Technical Audit

### Cascade and specificity

- The stylesheet is divided into `reset`, `tokens`, `base`, `components`, and `utilities` cascade layers.
- Styling uses low-specificity class selectors.
- There are no IDs used as CSS selectors.
- There is no `!important`.

### Relative units

Typography, padding, gaps, borders, radii, shadows, and layout dimensions use relative units. The stylesheet contains no `px` declarations.

### Color and WCAG contrast

The principal calculated pairs are approximately:

| Mode | Foreground and background | Approximate ratio |
|---|---|---:|
| Light | `oklch(22% 0.03 260)` on `oklch(97% 0.02 255)` | 15.86:1 |
| Dark | `oklch(94% 0.02 255)` on `oklch(18% 0.03 260)` | 15.80:1 |
| Light button | `oklch(99% 0 0)` on `oklch(48% 0.18 255)` | 6.40:1 |
| Dark button | `oklch(18% 0.03 260)` on `oklch(74% 0.14 255)` | 8.12:1 |

These pairs exceed the WCAG AA minimum of 4.5:1 for normal text.

### Fluid headline calculation

```css
--size-heading: clamp(1.75rem, 1.31rem + 1.878vw, 3rem);
```

The three parts are:

1. Minimum: `1.75rem`
2. Fluid engine: `1.31rem + 1.878vw`
3. Maximum: `3rem`

For a 16-rem root size, the formula targets about 1.75rem at a 375-wide viewport and 3rem at a 1440-wide viewport. The `rem` component allows browser zoom to enlarge the type instead of freezing it to viewport width.

### Optical text trimming and fallback

The badge and button have ordinary `line-height` and `em` padding as a fallback. Supporting browsers receive:

```css
@supports (text-box: trim-both cap alphabetic) {
  .article-card__badge,
  .article-card__button {
    text-box: trim-both cap alphabetic;
  }
}
```

To compare both modes in DevTools:

1. Inspect the badge or button.
2. Find the `text-box` declaration.
3. Uncheck it to view the fallback.
4. Check it again to compare the optically trimmed version.
5. If the browser does not support it, the declaration will not appear as active and the fallback remains readable.

## Deployment

1. Create a public organization repository named `ai-typographic-card`.
2. Upload or push all project files.
3. Open **Repository Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select `main` and `/(root)`.
6. Save and wait for deployment.

## Testing

See [`TESTING-CHECKLIST.md`](TESTING-CHECKLIST.md) for the complete manual audit.

The separate “Web Project Testing & Quality Assurance Guide” was not included with the assignment text provided here. The included checklist covers every test explicitly stated in the assignment plus common accessibility, responsive, and performance checks.

## Author

**Blen Hadgu**
