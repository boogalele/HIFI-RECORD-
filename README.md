# HIFI RECORD

Web prototype for rapid vinyl price assessment in a record shop.

## Current scope

- Minimal mobile-first interface for photo-based record intake.
- Explicit user confirmation before analysis.
- Separate Europe and USA market views.
- Price rules based on active VG+ listings, completed-sale frequency, and a WANTED evidence signal.
- Flag high asking prices without confirmed sales as `DA CONTROLLARE`.

## Important status

This repository is the project workspace. The existing HTML prototype is still a demo and is not yet connected to Discogs or a live identification service. Do not add Discogs tokens or other secrets to source files.

## Planned architecture

- Static web frontend.
- Backend service for protected Discogs credentials and API requests.
- Separate deterministic pricing rules, with source data and uncertainty shown clearly.
