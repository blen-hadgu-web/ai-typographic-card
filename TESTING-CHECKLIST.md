# Web Project Testing and Quality Assurance Checklist

This checklist is based on the assignment requirements supplied with the project. If the instructor provides a separate testing guide, add its required cases before recording.

## 1. Content and functionality

- [ ] The image loads and has meaningful alternative text.
- [ ] The category badge is visible.
- [ ] The headline is visible and readable.
- [ ] The description is visible.
- [ ] The “Read Article” control is keyboard-focusable.
- [ ] Selecting “Read Article” moves to the audit summary.
- [ ] The dark-mode switch changes all semantic colors.
- [ ] The dark-mode switch works with the keyboard.

## 2. Semantic HTML and accessibility

- [ ] The page has `header`, `main`, `article`, `section`, `aside`, and `footer` landmarks.
- [ ] Heading order is sequential: `h1`, followed by `h2`.
- [ ] The image includes descriptive `alt` text.
- [ ] The skip link appears when focused.
- [ ] Every interactive element has a visible focus indicator.
- [ ] The page remains usable at 200% browser zoom.
- [ ] Text does not overlap or disappear at 200% zoom.
- [ ] No page-level horizontal scrolling occurs at a narrow viewport.

## 3. Cascade and specificity

- [ ] `:root` contains the design tokens.
- [ ] The stylesheet uses cascade layers.
- [ ] Selectors remain low-specificity.
- [ ] No CSS selector relies on an HTML ID.
- [ ] The stylesheet contains no `!important`.

## 4. Relative units

- [ ] Typography uses `rem`, `em`, `vw`, or `clamp()`.
- [ ] Padding and gaps use relative units.
- [ ] Borders use relative units such as `0.0625rem`.
- [ ] Layout dimensions use `%`, `rem`, viewport, or container-query units.
- [ ] A search for `px` in `styles.css` returns no results.

## 5. Color and contrast

- [ ] Background, text, border, shadow, focus, and accent colors use `oklch()`.
- [ ] Light body text contrast is approximately 15.86:1.
- [ ] Dark body text contrast is approximately 15.80:1.
- [ ] Light button contrast is approximately 6.40:1.
- [ ] Dark button contrast is approximately 8.12:1.
- [ ] Focus indicators are clearly visible in light and dark modes.

## 6. Fluid typography

- [ ] The headline uses `clamp()`.
- [ ] The first value is the minimum.
- [ ] The middle value mixes `rem` and `vw`.
- [ ] The last value is the maximum.
- [ ] The headline grows smoothly as the viewport becomes wider.
- [ ] The headline still grows when the browser is zoomed.

## 7. Responsive layout

Test at approximately these browser widths:

- [ ] Narrow phone
- [ ] Large phone
- [ ] Tablet
- [ ] Laptop
- [ ] Wide desktop

Verify:

- [ ] The card is stacked at narrow sizes.
- [ ] The card becomes two columns when its container is wide enough.
- [ ] The image remains cropped appropriately.
- [ ] Content does not overflow the card.
- [ ] The theme control remains reachable.

## 8. Text trimming

- [ ] The badge has a normal line-height and padding fallback.
- [ ] The button has a normal line-height and padding fallback.
- [ ] `text-box: trim-both cap alphabetic` is inside `@supports`.
- [ ] In a supporting browser, disable `text-box` in DevTools and compare.
- [ ] Re-enable `text-box` and confirm the text appears optically tighter.
- [ ] In a non-supporting browser, confirm the fallback remains readable.

## 9. Motion preferences

- [ ] Enable reduced motion in the operating system or DevTools.
- [ ] Confirm the arrow animation is removed.

## 10. Production and deployment

- [ ] The repository is public.
- [ ] `index.html` is at the repository root.
- [ ] The live URL works in an Incognito/Private window.
- [ ] CSS and the local SVG image load over HTTPS.
- [ ] The favicon appears.
- [ ] GitHub Pages reports a successful deployment.
- [ ] The README explains the project, local use, AI prompt, audit, and deployment.
