# Shadows
Spoken text from the video, recorded 2026-11-25.

1. Stack two shadows
Stop using one shadow. Stack 2 instead. A tight 1, 1 pixel down with 2 blur for contact. A wide 1, 8 down with 24 of blur for lift. box-shadow: 0 1px 2px rgba(24,24,27,.08), 0 8px 24px rgba(24,24,27,.08)

2. Tint, don't blacken
Stop using black at 25%. Tint the shadow with your background hue around 8%. zinc-900, not black. rgba(24,24,27,.08)

3. Light from above
Light comes from above. Positive Y offset, 0 X offset on every shadow in the app, so nothing looks lit by two suns. x: 0, y: +

4. A scale, not a guess
Elevation is a scale, not a guess. Card, dropdown, modal, each gets one shadow token and no component gets a custom value. shadow-1 Card, shadow-2 Dropdown, shadow-3 Modal

5. Dark mode
In dark mode, shadows vanish. Raise elevation with a lighter surface instead, plus a 1 pixel top border instead. background: #18181B, border-top: 1px rgba(255,255,255,.1)

Closing line: Or let Claude Code fix yours. /restyle, UX Engine, Claude Code plugin, kills muddy shadows and the AI look.
