# SNPIS Vue Admin Design Rules

Rules the user set for the SNPIS Vue frontend (snpis-vue-frontend.vercel.app) on 2026-11-23. Apply them to every SNPIS frontend change so the same mistakes are never repeated.

## Tables: one line, nothing lost

- Every table row is ONE line. Cells never wrap or break a line; the table scrolls sideways instead.
- An ID shows ONLY its first 8 characters plus …. Nothing more, in every table and detail page.
- Long text such as an address is cut at the END with ….
- Hover popup is allowed ONLY for the ID (and the QR code popup). Address and other long text get NO hover popup; their full readable data lives on the record detail page.
- Hover an ID and the FULL ID shows in a popup box. Click or tap an ID and the FULL ID is copied.
- Copy feedback is a small Copied chip AT the clicked cell, in that place only. Never a center popup, never a page banner.
- Nested objects NEVER display as raw JSON with brackets. They display as readable data: the object's name when it has one, or key: value lines. Detail pages flatten nested objects into dotted label rows.
- Click a plain value (role, status, name) to FILTER the table by that column and value. The active filter shows as a chip with a Clear button.
- Click a column title to SORT by that column; click again to reverse.
- Filter and sort apply to the loaded page of rows.

## Icons

- Icons are TWO TONE Keyline style: a dark outline with a soft color fill. NEVER solid filled, the user rejected solid fill on 2026-11-23.
- The fill color follows the STATUS the icon shows: blue tones for normal and healthy, red tones for a problem, white on blue buttons.
- A few open-line icons (check, plus, search, eye, pencil, trash, logout, send, chevrons, key) stay stroke-only so they do not turn into blobs; their stroke still follows the status tone.
- Everywhere: icon plus short title together, consistent in sidebar, cards, buttons and page headers.

## Stable blocks, no glitch

- Blocks respect each other: a block never jumps, grows or pushes its neighbours when its data arrives. Every card keeps a fixed minimum height from the first paint, the loading state is the same size as the loaded state, and bars and detail lines are always rendered (empty until the number lands). Layout shift while loading is a design bug.

## Loading

- Data comes from the API and can take a few seconds. Everywhere data loads, show the loading spinner with a short label (Loading data, Loading settings, Loading profile) so the user sees fetching is happening. Never leave a blank or frozen looking page.
- Dashboard totals and sidebar numbers show the spinner until the real count arrives, never a fake number.
- The spinner is the ONE allowed animation in the app, and only for loading.

## Avatars

- Employees and users have avatar photos. People collections (employees, users) lead the table with a round avatar photo; when a record has no photo URL, show a blue circle with the person's initials.
- An avatar or photo field inside a record shows as the photo itself in the table and in the detail view (big, round), never as a raw URL line.

## QR codes

- QR Displays and QR Scans show the REAL QR code, generated from the record's token or payload value with the qrcode library: a small QR in the table row, a big QR in the detail view.
- Hover a QR in the table and a big QR popup shows, with the value under it.

## Columns the user can adjust

- Like Excel: the user can drag the right edge of a column header to resize that column. Never lock column widths; respect the user's space.
- Table headers stay ONE line: no wrapping, no dropdowns inside the header. Sorting stays a plain click on the title.

## Dashboard

- Top metric cards first: Total Records, Collections, Endpoints, Your Role.
- System Watch card for the admin watching the system: health status chip, uptime, health fields, plus Meta and Analytics cards.
- Then ALL collections grouped by their group, each card icon plus title plus its record count. Display all the data the admin has; do not hide collections.

## Sidebar

- Icon plus title only for every collection. NO record counts in the sidebar, the user removed them on 2026-11-23: no numbers, no chips; the user opens a collection to see its data. Counts live on the dashboard only.

## Record detail page

- View on any record opens a DEDICATED detail page, /admin/<collection>/<id>, never an inline panel. It shows everything about the record: header card with avatar, name, ID chip and status, then an All data card with every field flattened into readable rows (big QR for QR fields, photo for avatar fields, ID rows copy on click), plus the record's actions and Delete.

## Settings screens

- Config and Security use the standard settings screen design: one column of section cards, each card icon plus title, rows with the label on the left and the control on the right, one Save button per section at the bottom right. Boolean settings use a true/false select. No scattered two-column form stacks.
- The user Settings page is grouped under named group headers: Account (profile display information), Preferences (language English/Khmer, table density, rows per page), Notifications (copy feedback, loading messages), Privacy (show avatars, ID hover popup), Security (2FA, Telegram, devices). Every preference is real, stored on the device, and honored across the app; group names and preference labels follow the chosen language.
- Settings open as a popup dialog (user chose this 2026-11-23), same for every role. The popup is a LARGE CENTERED dialog (1100px wide, 760px tall, never full screen) with TWO SIDES: LEFT the group list, RIGHT that group's page INSIDE the dialog, so the user sees and updates in place. Scrollbars inside the dialog are HIDDEN (content still scrolls). The same panel component also serves the /settings/<group> pages, so popup and page never differ. Groups: My Account, Notifications, Preferences (language, density, rows per page, region, copy feedback, loading messages; NO shortcut list), Security & Privacy (one group, password gate, privacy switches, Telegram bind/unbind and my devices INSIDE this group, 2FA with QR), System Settings (admin only), Danger Zone. There is NO separate Connections group.
- My Account: ADMIN and DIRECTOR can update their own profile (name, email, phone, bio, avatar URL) with a Save button via PATCH /users/<own id>; other roles see it read only. The API has NO self-edit endpoint for other roles and NO change-password endpoint: never fake those forms.
- The gate password is verified ONCE at the Security & Privacy gate and kept in memory only: 2FA disable and Telegram unbind send it silently (the API requires a password field there) and never ask the user again. 2FA setup reads the otpauth URI wherever the API puts it in the response (deep search), with a secret-based fallback.
- The 2FA flow is STAGED, one stage at a time: idle shows only Start setup; setup shows a method picker (QR code | OTP URI + secret) and the 6 digit code field, which VERIFIES BY ITSELF when 6 digits are typed (no Enable button); Disable is NEVER shown during setup, it appears only in the enabled state (including later visits when the account already has 2FA on). Backup codes stay HIDDEN (dots) until the user taps Show, display in a 2-column grid, and can be downloaded as TXT or PDF.
- Telegram bind is STAGED the same way: idle shows Bind Telegram; pending shows the bind token (click to copy) and a Check status button; bound shows an Active chip and Unbind only. On later visits the bound state must be detected from /auth/me. Both 2FA-on and Telegram-bound detection search the profile DEEPLY (any nested field name or shape the API returns), never just one top-level field.
- NO Settings button and NO Logout button in the top navigation bar. Logout lives INSIDE the settings popup, at the bottom of the left group list. The sidebar holds the logo at the top and, at the bottom, the USER BLOCK: avatar, username, and only the BEGINNING of the user ID (first 8 characters, never the full ID). Tapping the user block opens the settings popup.
- The SIDEBAR IS STICKY: the app shell is exactly viewport height, the sidebar never scrolls away, only the main content scrolls.
- NEVER put guideline or instruction text in the design: no helper notes like "Role is set by your admin", no sentences explaining where a button lives or how a page works. The UI shows data, labels and controls only.
- The system Config (API /settings sections, API base, Meta) lives INSIDE Settings as the "System Settings" group, visible only to ADMIN and DIRECTOR. There is no separate Config entry in the sidebar.
- Security and Privacy are ONE group named "Security & Privacy". Its page is behind a PASSWORD GATE: the user must verify the current password against the API login on EVERY entry to the group (switching away and back asks again; nothing is stored) before anything on the page shows.
- The API user model has NO avatar field: the signed-in user's avatar is an Avatar URL the admin sets on My Account, stored on this device only (lib/avatar.ts), and shown in the sidebar user block and the account header.
- Devices display as pretty sub-cards: icon, device name as the title, status chip, and the rest of the fields in a clean label/value grid, never one cramped line. Users can set up 2FA themselves, but users NEVER change or reset a password: password changes are ADMIN ONLY (admin flows live on the Users pages, e.g. unlock, reset 2FA). Role flows differ by API grant: e.g. device Approve shows only for ADMIN, DIRECTOR, OFFICER.

## Style, unchanged

- Black, white and blue only. Light only. No shadow, no hover effect, no animation. 4px radius. Real API data only, only after login. RBAC left to the backend registry.
- The only hover behaviour allowed is the ID popup and the QR popup in tables; they show data, they are not a visual effect.
- Pages are protected: no token means back to /login, and the API answers 401.

## Login errors in plain words

- 401 on login shows "Wrong username or password", 429 shows "Too many attempts", a bad 2FA code shows "Wrong 2FA code". Never show the raw backend error text on the login page.
