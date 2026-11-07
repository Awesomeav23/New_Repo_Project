# Roadmap — Group Trip Planner

16 weeks · 3 hrs/day · 5 days/week (~15 hrs/week, ~240 hrs total).
Working on weekends too? Pull work forward from later weeks.

## Stack

| Layer | Choice |
|---|---|
| Frontend | React + TypeScript (Vite), TanStack Query, Tailwind |
| Backend | Django + Django REST Framework |
| Real-time | Django Channels + Redis |
| Database | Postgres (Docker, port **5437**) |
| Maps | Leaflet + OpenStreetMap (Nominatim geocoding) |
| Background jobs | Celery + Redis |
| Deploy | Render/Railway (API, DB, Redis) + Netlify/Vercel (frontend) |

## Core data model

- **User**
- **Trip**: name, destination, dates, cover image
- **TripMember**: user + trip + role (owner / editor / viewer)
- **Invite**: token, expiry, usage limit
- **ItineraryItem**: day, time, type, title, location (lat/lng), notes, order
- **Poll** → **PollOption** → **Vote**
- **Comment**: on itinerary items and polls
- **Expense** → **ExpenseSplit**
- **PackingItem**: shared or personal, assigned to a member, packed yes/no
- **Attachment**: tickets and booking PDFs
- **Notification** / **Activity**

## Weekly rhythm

- **Mon–Thu:** one feature at a time, end to end (model → API → tests → UI).
- **Fri:** finish tests, refactor, update the README progress log, push, plan next week.
- If a week runs over, push its leftovers into the Friday sessions. Don't let them pile up.

---

## Month 1: Foundation + trips

### Week 1: Design + project setup
- [x] **Day 1:** user stories, screen list, first wireframe (05). Remaining screens tracked in `docs/screens.md`
- [ ] **Day 2:** database diagram (all tables and relationships), API endpoint sketch
- [ ] **Day 3:** monorepo, Docker Compose (Postgres + Redis), Django project, `.env` config, pre-commit hooks (ruff, black)
- [ ] **Day 4:** React + TS + Vite + Tailwind, routing, layout shell, basic UI components (Button, Input, Modal, Card)
- [ ] **Day 5:** GitHub Actions CI (lint + test), a first test on each side, README setup steps, tag `v0.0.1`

### Week 2: Auth
- [ ] Custom User model, sign up / log in / log out
- [ ] JWT access + refresh tokens
- [ ] React auth context, protected routes, form validation
- [ ] Password reset by email (console email backend locally)

### Week 3: Profiles + trips
- [ ] Profile with avatar upload
- [ ] Trip create / view / edit / delete, cover images
- [ ] My-trips dashboard with upcoming / past filters, empty states

### Week 4: Members + permissions
- [ ] Invite links (token, expiry, usage limit) and email invites
- [ ] Roles (owner / editor / viewer) enforced with DRF permission classes
- [ ] Member management, transferring ownership
- [ ] Permission tests for every role

**Milestone:** create a trip and invite a friend who joins it.

## Month 2: Planning

### Week 5: Itinerary basics
- [ ] Items grouped by day, item types (activity, food, transport, stay) with icons
- [ ] Start and end times, notes, time-zone handling

### Week 6: Drag and drop
- [ ] Reordering with dnd-kit, moving items between days
- [ ] Optimistic UI (update the screen right away, undo if the save fails)
- [ ] Warnings for overlapping times

### Week 7: Maps
- [ ] Leaflet map, geocoding search (Nominatim)
- [ ] Pins per day, a route line through the day's stops
- [ ] Clicking a pin opens its item

### Week 8: Polls + comments
- [ ] Single and multiple-choice polls, deadlines, results charts
- [ ] Turn the winning option into an itinerary item
- [ ] Comment threads on items and polls

**Milestone:** a group can actually plan a trip together.

## Month 3: Money + live collaboration

### Week 9: Expenses
- [ ] Equal / exact-amount / percentage / share-based splits
- [ ] Categories, receipt photos
- [ ] Per-trip budget with a progress bar

### Week 10: Balances + currency
- [ ] Multiple currencies with exchange rates (free API, cached daily)
- [ ] Settle-up algorithm with the fewest transfers (write tests first)
- [ ] Mark payments as settled, spending charts

### Week 11: Real-time
- [ ] Django Channels + Redis, one WebSocket room per trip
- [ ] Live updates for itinerary edits, votes and expenses
- [ ] Show who's online, reconnect after a dropped connection

### Week 12: Packing + files
- [ ] Shared and personal packing lists, assigning items, list templates
- [ ] Ticket and booking uploads (S3-compatible storage, presigned URLs), document previews

**Milestone:** a multi-user app that updates live on everyone's screen.

## Month 4: Polish + ship

### Week 13: Notifications
- [ ] Activity feed, in-app notification bell
- [ ] Email notifications sent in the background with Celery, per-user notification settings
- [ ] Weather forecast on each trip day

### Week 14: Exports + UX
- [ ] PDF itinerary export, calendar (.ics) export
- [ ] Dark mode, mobile-friendly layouts
- [ ] Installable app (PWA) with offline viewing
- [ ] Accessibility pass

### Week 15: Hardening
- [ ] Playwright tests of full user flows
- [ ] Rate limiting, security headers
- [ ] Query optimization (`select_related`, removing duplicate queries), error tracking with Sentry

### Week 16: Ship
- [ ] Deploy backend, database and Redis + frontend
- [ ] Seeded demo account
- [ ] README with screenshots, demo GIF, architecture diagram
- [ ] Portfolio write-up, tag `v1.0.0`

**Milestone:** live on the internet, with a link you can share.
