## 2025-05-18 - Ambiguous "Book" Buttons
**Learning:** In the flight schedule, repetitive "Book" buttons create a confusing experience for screen reader users, as they hear "Book" 15 times without context.
**Action:** Always include specific context in `aria-label` for repeated actions (e.g., "Book Flight SN101 to Lüderitz" instead of just "Book").

## 2025-05-23 - Skip Links & Programmatic Focus
**Learning:** Adding a "Skip to Content" link is a high-impact accessibility win, but the target container must have `tabindex="-1"` to ensure focus moves correctly in all browsers/screen readers.
**Action:** Always add `tabindex="-1"` to the target of a skip link if it's not natively focusable.
