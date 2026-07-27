# Video Demonstration Script

Target length: approximately 3–5 minutes.

## 1. Introduction

“Hi, my name is Blen Hadgu. This is my AI-Co-Piloted Typographic Card. I acted as the technical lead by prompting AI to draft the code and then auditing and correcting the result.”

## 2. Functionality walkthrough

Open the live website and show:

1. The illustration
2. The Accessibility badge
3. The fluid article headline
4. The description
5. The Read Article button
6. The light/dark switch

Resize the browser to show the stacked and two-column layouts.

## 3. Cascade and source-code audit

Open `styles.css` in GitHub or VS Code and show:

- `@layer reset, tokens, base, components, utilities`
- Custom properties in `:root`
- Low-specificity class selectors
- No `!important`
- A search for `px` returning no CSS results

Say:

“The tokens are inherited through custom properties. The classes remain low-specificity, and the cascade layers control precedence without `!important`.”

## 4. Color verification

Show the light and dark OKLCH variables and the contrast table in the README.

Say:

“The main light and dark text pairs are approximately 15.86-to-1 and 15.80-to-1. The button pairs are approximately 6.40-to-1 and 8.12-to-1, so all exceed the 4.5-to-1 WCAG AA requirement.”

## 5. Fluid typography

Show:

```css
--size-heading: clamp(1.75rem, 1.31rem + 1.878vw, 3rem);
```

Explain:

“The first value is the minimum, the middle expression is the fluid engine, and the final value is the maximum. The middle combines rem and viewport width so browser zoom remains effective.”

Zoom the browser to 200% and show that the type grows without breaking the layout.

## 6. Text-box verification

Inspect the badge or button in DevTools.

- Show the fallback `line-height` and padding.
- Locate `text-box: trim-both cap alphabetic`.
- Disable and re-enable the property if the browser supports it.

Say:

“The `text-box` feature is progressive enhancement. Unsupported browsers keep the readable line-height and padding fallback.”

## 7. Testing checklist

Open `TESTING-CHECKLIST.md` and briefly show completed cases:

- Content
- Keyboard
- 200% zoom
- Responsive sizes
- Contrast
- Relative units
- Reduced motion
- Live deployment

## 8. Deployment proof

Show the public GitHub repository and the live GitHub Pages URL. Open the live URL in an Incognito window.

## 9. Closing

“The site meets the required modern CSS, accessibility, responsive, and deployment checks. Thank you.”
