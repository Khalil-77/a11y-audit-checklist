# E-commerce Accessibility Audit Checklist (WCAG 2.2 AA)

A practical checklist for auditing online stores, especially Shopify, against **WCAG 2.2 Level AA**. It is organized by the pages and components shoppers actually use, not by success criterion number, so you can work through a store page by page.

Automated tools (axe, WAVE, Lighthouse) catch only part of the issues. Most items below need manual testing with a keyboard and a screen reader.

## How to use

1. Pick the key templates: home, collection, product, cart, checkout, search, account, and one content page.
2. Test each one with keyboard only, a screen reader (NVDA or VoiceOver), 200% and 400% zoom, and a mobile device.
3. Log each failure with: page, element, WCAG criterion, impact on users, and recommended fix.

---

## 1. Global (every page)

- [ ] Page has a unique, descriptive `<title>` (2.4.2)
- [ ] `<html lang>` is set correctly (3.1.1)
- [ ] Skip link to main content is present and works (2.4.1)
- [ ] Landmarks are used: `header`, `nav`, `main`, `footer` (1.3.1)
- [ ] Headings form a logical outline with one `h1` (1.3.1, 2.4.6)
- [ ] All functionality works with keyboard only, with no keyboard traps (2.1.1, 2.1.2)
- [ ] Focus order follows the visual order (2.4.3)
- [ ] Focus indicator is clearly visible on every interactive element (2.4.7)
- [ ] Focused elements are not hidden behind sticky headers, cookie banners, or chat widgets (2.4.11)
- [ ] Text contrast is at least 4.5:1, or 3:1 for large text (1.4.3)
- [ ] Icons, input borders, and focus indicators have at least 3:1 contrast (1.4.11)
- [ ] Content reflows at 320px width with no horizontal scrolling (1.4.10)
- [ ] Text can be resized to 200% without loss of content (1.4.4)
- [ ] Text spacing overrides don't break the layout (1.4.12)
- [ ] Color is not the only way information is shown (1.4.1)
- [ ] Links make sense from their text or context, with no bare "Click here" or "Read more" (2.4.4)
- [ ] Touch targets are at least 24×24px, or have enough spacing (2.5.8)
- [ ] Content that appears on hover or focus can be dismissed and hovered (1.4.13)

## 2. Header and navigation

- [ ] Menu toggle is a `<button>` with an accessible name and `aria-expanded` (4.1.2)
- [ ] Dropdown and mega menus open and close with the keyboard, and Escape closes them
- [ ] Current page is indicated with `aria-current="page"` (1.3.1)
- [ ] Icon-only links and buttons (search, account, cart) have accessible names (1.1.1, 4.1.2)
- [ ] Cart count is announced as part of the cart link's name, e.g. "Cart, 2 items"
- [ ] Navigation is consistent across pages (3.2.3, 3.2.4)

## 3. Announcement bars, sliders, and carousels

- [ ] Auto-rotating content can be paused, stopped, or hidden (2.2.2)
- [ ] Previous, next, and pagination controls are buttons with accessible names
- [ ] Hidden slides are not reachable by keyboard or screen reader
- [ ] Motion respects `prefers-reduced-motion` (good practice; 2.3.3 is AAA)

## 4. Images and media

- [ ] Informative images have meaningful alt text (1.1.1)
- [ ] Decorative images have `alt=""` (1.1.1)
- [ ] Product images describe the product, not the file name
- [ ] Images of text are avoided, or the text is in the alt text (1.4.5)
- [ ] Videos have captions (1.2.2) and audio description or a transcript (1.2.5)
- [ ] Autoplaying video with sound can be paused or muted (1.4.2)

## 5. Collection and search results

- [ ] Product cards have one clear link, with no duplicate links for image and title
- [ ] Prices clearly say sale vs. regular price to screen readers (1.3.1)
- [ ] "Sold out" and "Sale" badges are available as text, not color only (1.4.1)
- [ ] Filters and sort controls are labelled and keyboard operable (3.3.2, 2.1.1)
- [ ] Result count updates are announced with a live region (4.1.3)
- [ ] Applied filters can be seen and removed with the keyboard
- [ ] "Load more" or infinite scroll keeps focus in a sensible place

## 6. Product page

- [ ] Product title is the `h1`
- [ ] Variant pickers (size, color) use real form controls with visible labels (1.3.1, 3.3.2)
- [ ] Color swatches have text names, not only colors (1.4.1)
- [ ] Unavailable variants are announced as unavailable
- [ ] Price and availability changes after selecting a variant are announced (4.1.3)
- [ ] Quantity input has a label, and +/- buttons have accessible names
- [ ] Add to cart gives feedback that screen readers announce (4.1.3)
- [ ] Image gallery and zoom work with the keyboard, and thumbnails have names
- [ ] Tabs and accordions (description, shipping, reviews) use correct ARIA patterns
- [ ] Size charts and other modals are accessible dialogs (see section 9)

## 7. Cart and cart drawer

- [ ] Cart drawer moves focus into the drawer, traps it, and returns it on close
- [ ] Each line item's remove button names the product, e.g. "Remove Blue T-shirt"
- [ ] Quantity changes and totals updates are announced (4.1.3)
- [ ] Discount code field has a label and announces errors (3.3.1)

## 8. Forms (newsletter, contact, account, checkout)

- [ ] Every input has a visible, programmatically associated label (1.3.1, 3.3.2)
- [ ] Required fields are indicated in text, not only with color or an asterisk
- [ ] Errors are identified in text and linked to the field (3.3.1)
- [ ] Error messages suggest how to fix the problem (3.3.3)
- [ ] `autocomplete` attributes are set on personal data fields (1.3.5)
- [ ] Users don't have to re-enter information already provided (3.3.7)
- [ ] Login doesn't depend on a cognitive test like a puzzle CAPTCHA without an alternative (3.3.8)
- [ ] Success messages are announced (4.1.3)

## 9. Modals and popups (newsletter, age gate, quick view)

- [ ] Uses `role="dialog"` or `<dialog>` with an accessible name
- [ ] Focus moves into the modal on open and returns to the trigger on close
- [ ] Focus is trapped inside while open, and Escape closes it
- [ ] Close button has an accessible name and is reachable early in the tab order
- [ ] Background content is inert while the modal is open

## 10. Third-party apps

- [ ] Review widgets, chat, wishlists, and loyalty apps pass the same checks
- [ ] Note the app name and vendor for any failure you can't fix in the theme
- [ ] Check the store's cookie or consent banner is keyboard and screen reader accessible

---

## Recommended tools

- **Automated:** axe DevTools, WAVE, Lighthouse, Accessibility Insights for Web
- **Screen readers:** NVDA (Windows), JAWS (Windows), VoiceOver (macOS / iOS), TalkBack (Android)
- **Contrast:** TPGi Colour Contrast Analyser
- **Shopify:** Theme Check in Shopify CLI for theme-level linting

## References

- [WCAG 2.2](https://www.w3.org/TR/WCAG22/)
- [WAI-ARIA Authoring Practices Guide](https://www.w3.org/WAI/ARIA/apg/)
- [Shopify theme accessibility best practices](https://shopify.dev/docs/storefronts/themes/best-practices/accessibility)

## License

CC BY 4.0. Free to use and adapt with attribution.

---

Maintained by [Muhammad Khalil Akbar](https://github.com/Khalil-77), Web Accessibility Specialist & Shopify Developer. Need an audit or remediation for your store? [Get in touch on LinkedIn](https://www.linkedin.com/in/muhammad-khalil-akbar-0b6858211).
