# Group Trip Planner

A full-stack app for planning trips with friends: a shared itinerary, a map, polls, split expenses
and packing lists, all updating live for everyone in the trip.

Built just for fun over 16 weeks. See [ROADMAP.md](ROADMAP.md) for the plan.

## Docs
- [User stories](docs/user-stories.md)
- [Screens](docs/screens.md)

## How we work
- **Claude drafts** wireframes, the database diagram and the API endpoint list.
- **I review** the drafts and note changes.
- **I build** by typing the commands and code myself, with step-by-step guidance in chat.

## Next session (about 2.5–3 hrs)
- [ ] **Review drafts** (20 min): 06 Itinerary + 10 Expenses wireframes, database diagram
- [ ] **Check tools** (15 min): Python 3.12+, Node 20+, Docker Desktop, VS Code (`python3 --version`, `node -v`, `docker -v`)
- [ ] **Project folders** (10 min): `backend/`, `frontend/`, `.gitignore`, `.env.example`
- [ ] **Database in Docker** (30 min): `docker-compose.yml` with Postgres (port 5437) + Redis, `docker compose up -d`, connect to prove it works
- [ ] **Django project** (45 min): virtual environment, install Django + DRF + psycopg + django-environ, settings from `.env`, connect to Postgres, `migrate`, admin user, log into `/admin`
- [ ] **First model** (30 min): `trips` app with the Trip model, `makemigrations` + `migrate`, register in admin, create a test trip
- [ ] **Commit + push by hand** (10 min): `git add`, `git commit`, `git push`

Note: Day 2's design work becomes review only, and Day 3's setup starts early. That puts us ahead of the roadmap.

## Progress log

| Date | Week / Day | Done |
|---|---|---|
| 2026-11-06 | W1 · Day 1 | Roadmap, user stories, screen list, trip overview wireframe (other screens tracked in docs/screens.md) |
