# M3 Expressive Web Color Design

Source guides, followed for this web design look:
https://m3.material.io/
https://m3.material.io/styles/color/roles

## Idea

Use Material Design 3 color roles for the web.
A role is a named job for a color, not a fixed color by itself.
Use the role name in code, and let the theme supply the value.
This keeps text readable, keeps contrast accessible, and lets one layout work in light theme, dark theme, and dynamic color.

## M3 Expressive

M3 Expressive means design with emotion.
It adds:
- Vibrant colors
- Intuitive motion
- Adaptive components
- Flexible typography
- Contrasting shapes

Goal: a product that is more usable and more engaging, not only correct.

## Baseline scheme and dynamic color

Baseline color scheme:
- The default static scheme.
- It does not dynamically change from user content.
- Primary, on primary, primary container, and on primary container are shown in the baseline light theme color scheme in the reference image.

Dynamic color scheme:
- The scheme changes from an input, such as a wallpaper or in app content.
- One input color can generate a full accessible scheme and assign colors to UI elements.
- Benefits: personalized UI, accessible contrast, user controlled contrast, automatic dark theme.

Static colors inside dynamic color:
- Some colors can stay fixed by design, such as semantic colors.
- Error roles are static by default in a dynamic scheme, but they still adapt for light and dark theme.

## More colorful container text and icons

In light theme, these roles are more colorful while still keeping accessible contrast:
- On primary container
- On secondary container
- On tertiary container
- On error container

Affected components:
Badges, buttons, extended FAB, FAB, icon buttons, segmented buttons, chips, lists, menus, navigation bar, navigation drawer, navigation rail, switches, toolbars.

## Core color roles

Primary, for the most important actions and emphasis:
- Primary: high emphasis fills, text, and icons on surface. Use for FAB, filled buttons, active states.
- On primary: text and icons on primary.
- Primary container: standout fill on surface, for key components like FAB.
- On primary container: text and icons on primary container.

Secondary, for less prominent parts:
- Secondary: less prominent fills, text, and icons on surface.
- On secondary: text and icons on secondary.
- Secondary container: recessive fill, for tonal buttons and filter chips.
- On secondary container: text and icons on secondary container.

Tertiary, for contrasting accents:
- Tertiary: complementary fills, text, and icons on surface. Use for badges, notifications, and input accents.
- On tertiary: text and icons on tertiary.
- Tertiary container: complementary container fill on surface.
- On tertiary container: text and icons on tertiary container.

Error, for error states only:
- Error: urgent fills, text, and icons on surface.
- On error: text and icons on error.
- Error container: urgent container fill on surface.
- On error container: text and icons on error container.

## Fixed accent roles

Fixed roles keep the same tone in light and dark theme.
Use them only when that fixed behavior is wanted, and check contrast with care.

- Primary fixed, primary fixed dim, on primary fixed, on primary fixed variant
- Secondary fixed, secondary fixed dim, on secondary fixed, on secondary fixed variant
- Tertiary fixed, tertiary fixed dim, on tertiary fixed, on tertiary fixed variant

Fixed dim is the stronger, more emphasized tone of the fixed color.

## Surface roles

Surfaces are backgrounds and large, low emphasis areas.
Containers are fills for cards, sheets, dialogs, and components. Never use a container role for text or icons, use its on role.

- Surface dim: dimmest surface.
- Surface: default background.
- Surface bright: brightest surface.
- Surface container lowest: lowest emphasis container.
- Surface container low: low emphasis container.
- Surface container: default container.
- Surface container high: high emphasis container.
- Surface container highest: highest emphasis container.
- On surface: main text and icons on any surface or surface container.
- On surface variant: lower emphasis text and icons on any surface or surface container.

Keep the same surface mapping for the same layout region on mobile, tablet, and desktop.

## Inverse, outline, scrim, shadow

- Inverse surface: background that contrasts against the normal surface, such as a snackbar.
- Inverse on surface: text and icons on inverse surface.
- Inverse primary: action color on inverse surface.
- Outline: important boundaries, such as a text field border. Needs clear contrast.
- Outline variant: decorative dividers and quiet borders. Do not use it alone to define a target boundary.
- Scrim: the dim layer behind a modal.
- Shadow: shadow color for elevation.

## Pairing rules

- Always pair a fill with its own on color. Primary with on primary, primary container with on primary container, and so on.
- Never put a container color as text on another container color.
- Wrong pairing breaks contrast when the theme or contrast level changes.
- Roles are built as accessible pairs, with at least 3 to 1 contrast for paired UI colors, and text pairs should reach 4.5 to 1 where the role design requires it.
- Variant means lower emphasis than its pair. On means content sitting on top of the named color. Container means a fill for a foreground element.

## Web tokens

Name CSS variables by role, never by raw color:

--md-sys-color-primary
--md-sys-color-on-primary
--md-sys-color-primary-container
--md-sys-color-on-primary-container
--md-sys-color-secondary
--md-sys-color-on-secondary
--md-sys-color-secondary-container
--md-sys-color-on-secondary-container
--md-sys-color-tertiary
--md-sys-color-on-tertiary
--md-sys-color-tertiary-container
--md-sys-color-on-tertiary-container
--md-sys-color-error
--md-sys-color-on-error
--md-sys-color-error-container
--md-sys-color-on-error-container
--md-sys-color-surface
--md-sys-color-surface-dim
--md-sys-color-surface-bright
--md-sys-color-surface-container-lowest
--md-sys-color-surface-container-low
--md-sys-color-surface-container
--md-sys-color-surface-container-high
--md-sys-color-surface-container-highest
--md-sys-color-on-surface
--md-sys-color-on-surface-variant
--md-sys-color-inverse-surface
--md-sys-color-inverse-on-surface
--md-sys-color-inverse-primary
--md-sys-color-outline
--md-sys-color-outline-variant
--md-sys-color-scrim
--md-sys-color-shadow

Set the values from the baseline light scheme in the reference image for light theme, and from the matching dark scheme for dark theme. Change only the values, never the role names, when the theme changes.

## Web component mapping

- Filled button: primary fill, on primary text and icon.
- FAB and extended FAB: primary container fill, on primary container icon and text.
- Tonal button: secondary container fill, on secondary container text.
- Badge: tertiary or error, with its matching on color.
- Chips: secondary container for selected or recessive chips, outline for the border.
- Cards and dialogs: surface container levels, on surface text, on surface variant for quiet text.
- Navigation bar, drawer, and rail: surface container background, secondary container for the selected item, on surface for labels.
- Menus and lists: surface container background, on surface text, outline variant dividers.
- Switches and segmented buttons: primary for the on or selected state, surface container and outline for the off state.
- Toolbars: surface or surface container background, on surface actions, primary for the main action.
- Snackbar: inverse surface background, inverse on surface text, inverse primary action.
- Text fields: surface container fill, on surface text, outline border, error roles only in the error state.

## Reference image

The user supplied image shows the full baseline light scheme grid: primary, secondary, tertiary, and error groups with their containers and on colors, the fixed and fixed dim groups, surface dim, surface, and surface bright, the five surface container levels, inverse surface, inverse on surface, inverse primary, on surface, on surface variant, outline, outline variant, scrim, and shadow.
