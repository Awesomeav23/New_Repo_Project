# Screens

Every screen in the app and what goes on it. Sketch each one (paper or Excalidraw), then save
the wireframes to `docs/wireframes/` (e.g. `06-itinerary.png`).

Story IDs refer to `user-stories.md`.

## Wireframe status

Sketch each screen before the week its feature is built.

| # | Screen | Wireframe | Sketch by |
|---|---|---|---|
| 01 | Landing | ☐ To do | Week 16 |
| 02 | Sign up / Log in / Reset | ☐ To do | Week 2 |
| 03 | My trips dashboard | ☐ To do (re-add from earlier sketch) | Week 3 |
| 04 | Create / edit trip | ☐ To do | Week 3 |
| 05 | Trip overview | ✅ [Done](wireframes/05-trip-overview.png) | — |
| 06 | Itinerary | ☐ To do (next, before Day 2) | Week 5 |
| 07 | Itinerary item | ☐ To do | Week 5 |
| 08 | Map | ☐ To do | Week 7 |
| 09 | Polls | ☐ To do | Week 8 |
| 10 | Expenses | ☐ To do (next, before Day 2) | Week 9 |
| 11 | Packing | ☐ To do | Week 12 |
| 12 | Files | ☐ To do | Week 12 |
| 13 | Members + invite | ☐ To do | Week 4 |
| 14 | Join trip | ☐ To do | Week 4 |
| 15 | Profile + settings | ☐ To do | Week 3 |

## Public

### 01 · Landing (`/`)
- Hero: one-line pitch + "Get started" button
- 3 feature highlights (plan together, split costs, live updates)
- Log in link in the navbar

### 02 · Sign up / Log in / Reset password (`/signup`, `/login`, `/reset`)
- Email + password form, validation errors inline
- Links between the three forms
- Stories: A1, A2, A3

## Logged in

### 03 · My trips dashboard (`/trips`)
- Tabs: Upcoming / Past
- Trip cards: cover image, name, dates, member avatars
- "New trip" button
- Empty state: "No trips yet — plan your first one"
- Stories: T2

### 04 · Create / edit trip (modal)
- Name, destination, start and end dates, cover image upload
- Stories: T1, T3, T4

### 05 · Trip overview (`/trips/:id`)
- Header: cover, name, dates, member avatars, "Invite" button
- Tab bar: **Itinerary · Map · Polls · Expenses · Packing · Files**
- Summary cards: days until the trip, open polls, your balance
- Activity feed (sidebar on desktop, below on mobile)
- Stories: C4

### 06 · Itinerary tab (`/trips/:id/itinerary`)
- One column per day (desktop) or one section per day (mobile)
- Item cards: type icon, time, title, location; drag handle
- "Add item" per day → item form (07)
- Overlap warning badge
- Stories: I1–I4, C1

### 07 · Itinerary item (drawer or modal)
- Type, title, start and end time, location search, notes
- Comments thread below
- Stories: I1, I6, D4

### 08 · Map tab (`/trips/:id/map`)
- Full-width map, pins colored by day, route line per day
- Day filter chips
- Clicking a pin opens the item
- Stories: I5

### 09 · Polls tab (`/trips/:id/polls`)
- Open polls first, then closed ones
- Poll card: question, options with vote bars, deadline, "Vote" button
- "Create poll" form; "Add to itinerary" on the winning option
- Stories: D1–D3

### 10 · Expenses tab (`/trips/:id/expenses`)
- Balance summary at top: "You owe Sam $40" / "Alex owes you $15"
- Budget progress bar
- Expense list: description, payer, amount, category, date
- "Add expense" form: amount, currency, payer, split type, per-person amounts
- "Settle up" view: the fewest transfers, "Mark paid" buttons
- Spending chart by category
- Stories: E1–E7

### 11 · Packing tab (`/trips/:id/packing`)
- Two lists: Shared / Mine
- Checkbox items, assignee avatar, "Add item"
- Stories: P1, P2

### 12 · Files tab (`/trips/:id/files`)
- Upload area, file list with type icon, uploader, date
- Preview on click
- Stories: P3

### 13 · Members + invite (modal, from the trip header)
- Copy invite link, invite by email
- Member list with role dropdowns (owner only), remove / leave
- Stories: M1, M3–M5

### 14 · Join trip (`/join/:token`)
- Trip preview (name, dates, who's going) + "Join trip" button
- If logged out: log in / sign up first, then return here
- Stories: M2

### 15 · Profile + settings (`/settings`)
- Name, avatar, password change
- Notification preferences, dark mode toggle
- Stories: A4, C5, X4

### Shared pieces
- **Navbar:** logo, My trips, notification bell (with dropdown), avatar menu
- **Notification dropdown:** latest notifications, "Mark all read"
- **Toasts** for success and error messages
- **Loading skeletons** for each list
