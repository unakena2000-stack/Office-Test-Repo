# Lucide Icons — Usage Guide

> Companion file to `lucide-icon-set.yaml` (icon names + import names + categories).
> This file covers **how and when** to use icons — the judgment calls a data file can't carry.

---

## 1. Import & Basic Usage

Icons come from the `lucide-react` package — never inline raw SVG paths, always import the component.

```jsx
import { Search, Trash2, AlertCircle } from "lucide-react";

<Search />
```

Look up the exact import name for any icon in `lucide-icon-set.yaml` before using it — icon names are PascalCase versions of their kebab-case file name (e.g. `alarm-clock-check` → `AlarmClockCheck`).

---

## 2. Sizing

Lucide icons default to `24x24`. Override with `size` prop or CSS — always use design tokens, never hardcoded pixel values.

```jsx
<Search size={16} />        // inline with body text
<Trash2 size={20} />        // standalone action icon
```

| Context | Recommended size | Token reference |
|---|---|---|
| Inline with body/label text | 14–16px | `icon.size.sm` |
| Default button/input icon | 16–18px | `icon.size.md` |
| Standalone icon-only action | 20–24px | `icon.size.lg` |

In the **480px iframe embed**, prefer the smaller end of this range — icons don't need to compete for space the way they might in a full-width desktop app.

---

## 3. Color

Icons inherit color via `currentColor` by default — this is almost always the right approach, since it keeps icon color in sync with surrounding text/button state without extra props.

```jsx
<AlertCircle className="text-destructive" />   // icon inherits the text color
```

Only override color directly when the icon carries semantic meaning independent of its text (e.g. a status dot-style icon). In that case, reference semantic color tokens:

```jsx
<CircleCheckIcon style={{ color: 'var(--color-semantic-status-success)' }} />
```

Never hardcode a hex value directly on an icon — always go through a token.

---

## 4. Icon-only vs. Icon + Label

| Use icon-only when... | Use icon + label when... |
|---|---|
| The action is universally recognizable (close ✕, search 🔍) | The action is ambiguous or destructive (delete, archive) |
| Space is extremely tight (toolbar, table row actions) | It's a primary action button |
| A tooltip is provided on hover/focus as backup | First-time user context (onboarding, empty states) |

**Rule of thumb for this product specifically:** given the 480px embed constraint, icon-only is common — but every icon-only interactive element MUST have an accessible label (see below). Don't rely on hover tooltips alone, since touch users can't hover.

---

## 5. Accessibility (required, not optional)

- **Icon-only buttons must have `aria-label`:**
  ```jsx
  <button aria-label="Delete item">
    <Trash2 size={16} />
  </button>
  ```
- **Decorative icons** (icon sits next to visible text that already conveys the meaning) should be hidden from screen readers:
  ```jsx
  <Search size={16} aria-hidden="true" />
  <span>Search</span>
  ```
- **Minimum tap target:** even if the icon itself is 16–20px, the clickable area should be at least 32–36px (padding around the icon) — this matters more in a narrow embed where precision taps are harder.

---

## 6. Choosing the Right Icon

Use the `categories` field in `lucide-icon-set.yaml` to narrow down candidates by context (e.g. `medical`, `text`, `account`, `social`). When multiple icons could fit:

1. Prefer the icon already used elsewhere in the product for that same action (consistency > novelty)
2. Check existing usage first — this codebase already uses:
   - `Search` → search inputs
   - `Trash2` → destructive/delete actions
   - `AlertCircle` → inline error state
   - `ChevronDownIcon` / `ChevronUpIcon` → expand/collapse, select dropdowns
   - `XIcon` → modal/dialog close
   - `Plus` → add new item
   - `CircleCheckIcon` / `InfoIcon` / `TriangleAlertIcon` / `OctagonXIcon` → toast/status variants (success/info/warning/error)
3. Don't introduce a new icon for an action that already has an established one elsewhere in the product

---

## 7. Do NOT

- Don't inline raw SVG markup when a Lucide icon already covers the need
- Don't hardcode `stroke-width`, `color`, or `size` values outside the token/prop system
- Don't use an icon as the *only* indicator of a destructive or irreversible action without a confirming label or modal
- Don't mix icon libraries — if it's not in `lucide-icon-set.yaml`, check with design before introducing a new source
