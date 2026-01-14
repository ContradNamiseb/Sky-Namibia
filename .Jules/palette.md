## 2025-05-18 - Ambiguous "Book" Buttons
**Learning:** In the flight schedule, repetitive "Book" buttons create a confusing experience for screen reader users, as they hear "Book" 15 times without context.
**Action:** Always include specific context in `aria-label` for repeated actions (e.g., "Book Flight SN101 to Lüderitz" instead of just "Book").

## 2025-05-23 - Skip Links & Programmatic Focus
**Learning:** Adding a "Skip to Content" link is a high-impact accessibility win, but the target container must have `tabindex="-1"` to ensure focus moves correctly in all browsers/screen readers.
**Action:** Always add `tabindex="-1"` to the target of a skip link if it's not natively focusable.

## 2025-05-24 - Interactive Elements Must Be Interactive
**Learning:** Social media icons implemented as pure `<i>` tags are invisible to keyboard users and screen readers. They look actionable but are dead pixels.
**Action:** Always wrap icon-only interactive elements in `<a>` or `<button>` tags with `aria-label` to ensure they are reachable and announce their purpose.

## 2025-05-25 - Accessible Tab Interfaces
**Learning:** Custom tab implementations often rely on visual classes like `.active` but fail to communicate state to screen readers, leaving them unaware of the tabbed content structure.
**Action:** Use the `role="tablist"`, `tab`, and `tabpanel` pattern with `aria-selected` and `aria-controls` to make tabs semantically rich and accessible.

## 2026-01-14 - Semantic Progress Indicators
**Learning:** Visual-only progress bars (implemented as divs with width styles) deprive screen reader users of critical status information (e.g., flight completion percentage).
**Action:** Always enhance custom progress indicators with `role="progressbar"`, `aria-valuenow`, `aria-valuemin`, `aria-valuemax`, and a descriptive `aria-label`.
