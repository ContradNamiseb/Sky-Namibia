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

## 2025-05-26 - Invisible Focus Traps
**Learning:** Using `opacity: 0` to hide interactive elements (like a "Back to Top" button) leaves them in the keyboard tab order, creating a "ghost" focus stop.
**Action:** Always pair `opacity: 0` with `visibility: hidden` (or `display: none`) to properly remove hidden elements from the accessibility tree.

## 2025-05-28 - Contextual Progress Bars
**Learning:** Generic labels like "Flight progress" on multiple status indicators are confusing for screen reader users who lack visual context.
**Action:** Include specific identifiers (like flight numbers) in `aria-label` for any status component that appears multiple times in a list.

## 2025-05-28 - Fragile Inline Handlers
**Learning:** Relying on global `event` objects in inline `onclick` handlers can be unreliable for targeting the triggering element.
**Action:** Explicitly pass `this` to the handler function (e.g., `onclick="handleClick(this)"`) to ensure robust element reference.

## 2025-05-28 - Noisy Decorative Characters
**Learning:** Decorative Unicode characters (like ➤, ✈️) and icons announce themselves noisily to screen readers (e.g., "Black Rightwards Arrowhead"), confusing the actual content.
**Action:** Always wrap decorative text characters in `<span aria-hidden="true">` and add the attribute to decorative icon tags.

## 2025-05-29 - Missing Keyboard Affordance on Cards
**Learning:** Interactive cards that use `:hover` to "lift" or transform often lack the same visual feedback for keyboard users, making the interface feel static and unresponsive to tab navigation.
**Action:** Always pair `:hover` transform effects with `:focus-within` on the container to ensure keyboard users perceive the same interactivity.

## 2026-01-26 - Prevent Duplicate Pull Requests
**Learning:** Automated sessions may open duplicate PRs if previous ones are not reviewed, creating noise.
**Action:** Before opening a PR, check for existing open PRs from "Palette" or on the same branch. If one exists, do not open a new one.

## 2025-05-30 - Focus Parity for Hover Effects
**Learning:** Decorative hover effects (like animated underlines on nav links) are often missed for keyboard users, making the interface feel less polished.
**Action:** Always mirror complex `:hover` styles (especially those on pseudo-elements like `::after`) with `:focus-visible` to ensure keyboard users get the same visual feedback.

## 2025-05-30 - Logo Must Be A Link
**Learning:** The main logo was implemented as a `div`, breaking the universal "Logo = Home" expectation.
**Action:** Ensure the main brand logo is always wrapped in an `<a>` tag pointing to the homepage, with `text-decoration: none` to preserve styling.
