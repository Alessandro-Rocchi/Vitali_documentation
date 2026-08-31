# 9. Usability, Accessibility & Heuristic Compliance

## 9.1  Usability Analysis

1. **Visibility of System Status:** Filter modifications immediately update map markers and display active result counters.
2. **Match Between System and Real World:** Geographic terminology conforms to official Parisian arrondissements, paired with recognized film taxonomy.
3. **User Control and Freedom:** Easy "Reset Filters" and "Clear Route" buttons restore default viewport settings at any stage.
4. **Consistency and Standards:** Uniform navigation headers and color palettes across all six sub-pages.
5. **Recognition Rather than Recall:** Location cards in `catalogue.html` display film poster thumbnails, minimizing memory strain.

## 9.2 Accessibility Auditing

* **Color Contrast:** All body text meets or exceeds the minimum 4.5:1 contrast ratio against light/dark themes.
* **Semantic Aria Attributes:** Screen readers are guided with `aria-expanded`, `aria-controls`, and `role="region"` attributes on dynamic drawers and modals.
* **Keyboard Navigability:** Interactive elements (popups, cards, sliders) are fully reachable via standard `Tab` / `Shift+Tab` and triggerable via `Enter` / `Space`.
