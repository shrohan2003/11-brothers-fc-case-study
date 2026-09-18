# 11 Brothers FC

My first paid real-world software project, developed for a football organization in Bangladesh.

I built the club platform as an individual project. It brings the public website, player accounts and club administration into one application.

## Key features

- Public pages for branches, players, matches, results, events, news, photos and videos.
- Email/password registration and login, player profiles and a personal dashboard.
- Match and event registration workflows, manual payment submission and staff verification.
- Server-side role checks for club-wide, branch and match responsibilities.
- Administrative pages for club content, players, registrations, payments and reports.
- Notifications and audit records for operational actions.

These features are present in the source. Local validation covered public pages, player registration and the player dashboard; it did not exercise every administrative or external-service workflow.

## Technology

| Layer | Implementation |
| --- | --- |
| Language | TypeScript |
| Interface | React, Vinext / Next-compatible routing, Tailwind CSS |
| Server | Cloudflare Workers and route handlers |
| Database | Cloudflare D1 with Drizzle schema and SQL migrations |
| Files | Cloudinary storage integration |
| Login | PBKDF2 password hashing and database-backed cookie sessions |

This project is written in TypeScript. Python is my main language across my wider portfolio.

## How it works

A browser request reaches a page or API handler. The server reads the session, checks the user's role and record access, and queries D1. Media workflows use a separate storage layer. Payment evidence is handled separately from public gallery images.

## Screenshots

The following screenshots show the real application running locally with seeded demonstration data and a disposable demonstration account. Counts, names and fixtures shown here are examples, not customer or usage statistics.

![Homepage](docs/screenshots/home.png)
![Matches](docs/screenshots/matches.png)
![Player dashboard](docs/screenshots/player-dashboard.png)
![Login](docs/screenshots/login.png)

## Validation and current limits

The reviewed source passed 12 business-policy tests, TypeScript checking, lint and a production build. The build also passed after the local-preview configuration fixes. Local database migrations and player account creation were then exercised. Cloudinary uploads, payment verification, password-reset email, administrative flows and production persistence require further end-to-end validation.

The standalone authentication integration also needs further hardening before making production-security claims. This case study does not claim a security audit or complete production acceptance.

## Development lessons

The project provides practical examples of relational data modeling, separating public and private data, checking role scope on the server, and keeping local preview data separate from production.

## Future improvements

Expand integration tests for authentication, registration capacity, payment verification and upload privacy; verify restore procedures and deployment acceptance checks.

## Source availability

This repository is a portfolio case study. Client application source, credentials and private records are not included.

## Author

Shanjidul Hasan Rohan · [GitHub](https://github.com/shrohan2003)
