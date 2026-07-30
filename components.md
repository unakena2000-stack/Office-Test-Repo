---
name: Component Library Reference
description: Reference for the CRM Figma component library (Button, Input, Dropdown, Checkbox, Radio, Toggle) with variants, states, Figma keys. Use when generating or reviewing UI code for this design system.
---

# Component Library Reference

Extracted from the Figma file **Source** (page: **Test**)
`https://www.figma.com/design/HMU6Pz7woPmkIlIKSLFRSh/Source?node-id=90768-18140`

> All six components below currently carry a **❌ prefix** in their Figma layer names, which typically marks them as deprecated / not yet approved in this file. Worth confirming with design before treating these as source-of-truth.

| Component | Variants | Variant Axes |
|---|---|---|
| [Button](#button) | 153 | Type, Size, State |
| [Radio Button](#radio-button) | 7 | State |
| [Input Field](#input-field) | 48 | Size, Type, State |
| [Checkbox](#checkbox) | 8 | State |
| [Dropdown](#dropdown) | 10 | State, Size |
| [Toggle](#toggle) | 8 | Switch, State |

---

## Button

- **Figma layer name:** ❌ Button
- **Aliases:** Buttons, Btn
- **Component key:** `43e98e00d56ac580b936d4d6558a92b03ff8781d`
- **Node ID:** `90768:18341`
- **Total variants:** 153

**Variant axes**

| Property | Values |
|---|---|
| Type | Primary Button, Default Button, Outline Blue Btn, Ghost Blue Btn, Negative Button, Outline Negative Btn, Ghost Negative Btn, Success Button, Outline Success Btn, Waning Button, Outline Warning Btn, More Icon Btn, More Primary Btn, More Default Btn, More Outline Blue Btn, Primary Link, Secondary Link, Negative Link, Default Link, Zia Primary, Zia Outline, Refresh Btn |
| Size | Default, Small, Extra Small |
| State | Default, Hover, Clicked, Loading, Disabled |

Note: not every Type/Size combination has all 5 states (e.g. `Waning Button` and `Outline Warning Btn` only exist at Small size; `Primary Link` / `Secondary Link` / etc. only have Default, Hover, Disabled). Treat the axis table as the full value set, not a strict cartesian product.

---

## Radio Button

- **Figma layer name:** ❌ Radio Button
- **Aliases:** Option Button, Radio, Radio Btn, Selection Button
- **Component key:** `cdd654832c2f4c5594b097589d444d0b0fa71e5a`
- **Node ID:** `90768:24514`
- **Total variants:** 7

**Variant axes**

| Property | Values |
|---|---|
| State | Default, Hover, Clicked, Disabled, Checked Disable, Focus, Checked Focus |

---

## Input Field

- **Figma layer name:** ❌ Input field - Not Approved
- **Aliases:** Text Field, Input, Form Field, Input Field
- **Component key:** `9be44e28c9c71a93709ba4cf024c31dab9c2c703`
- **Node ID:** `90768:21996`
- **Total variants:** 48

**Variant axes**

| Property | Values |
|---|---|
| Size | Small, Normal |
| Type | Currency, Field, Password Field, Header, Date & Time |
| State | Error, Disabled, Auto Update, Focused, Default, Hover |

Note: coverage is uneven across Type × Size × State — e.g. `Password Field` and `Header` only appear at `Normal` size, and not every Type has all six states populated.

---

## Checkbox

- **Figma layer name:** ❌ Checkbox
- **Aliases:** Tickbox
- **Component key:** `fe77554421e6bf0623a2d581047eeb51ee8264ef`
- **Node ID:** `90768:25611`
- **Total variants:** 8

**Variant axes**

| Property | Values |
|---|---|
| State | Default, Hover, Checked, Disabled, Checked Disable, Focus, Checked Focus, Indeterminate |

> Note: a second, non-❌-prefixed **Checkbox** component set also exists in this file (key `aab110e5fce086242dc828880e91720d14dba063`, node `15:503`, also 8 variants). This doc covers the Test-page (❌) version — let me know if you want the other one documented too.

---

## Dropdown

- **Figma layer name:** ❌ Dropdown
- **Aliases:** Drop down, Drop-down, Drop Down List, Picklist
- **Component key:** `bd3de72d7ee9145396e27a4e10e928bf3bcfb816`
- **Node ID:** `90768:25802`
- **Total variants:** 10

**Variant axes**

| Property | Values |
|---|---|
| State | Default, Hover, Active, Error, Disabled |
| Size | Default, Small |

---

## Toggle

- **Figma layer name:** ❌ Toggle
- **Aliases:** Toggle, Toggle Switch, Switch
- **Component key:** `ea789140ff36b26a586e713bdb47e67119b09453`
- **Node ID:** `90768:25695`
- **Total variants:** 8

**Variant axes**

| Property | Values |
|---|---|
| Switch | Off, On |
| State | Default, Hover (Only in interaction), Disabled, Focus |

---

## Companion Data File

A companion `components.yaml` (same field structure: `component_key`, `node_id`, `variant_axes`, etc.) is referenced for scripting/tooling use, but has **not yet been created or uploaded** — this section is a placeholder. Do not assume it exists until it's actually generated and placed alongside this skill file.
