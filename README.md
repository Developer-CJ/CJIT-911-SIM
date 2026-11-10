# CJIT Metrocoms 911 Simulator

**Emergency Communications & Public Safety Dispatch Simulation** — Powered by CJIT

A multi-agency 911 communications simulator featuring incident intake, simulated emergency calls, CAD workflows, unit dispatch and two-way radio traffic. Developed by **CJIT Solutions / CJIT Networks**.

> **Project status:** Active development. This repository currently holds project documentation; deployed application source and operational integration have not been verified in this repository.

## Project links

| Component | Intended URL |
| --- | --- |
| Main 911 simulator | https://911.cjitnetworks.com |
| Admin / configuration | https://admin.911.cjitnetworks.com |
| Radio gateway | https://radio.911.cjitservices.tech |
| AI radio service | https://radio.ai.911.cjitnetworks.com |

URLs are project targets, **not** proof of live availability.

## Product scope

- **Metrocoms** fictional dispatch center with CJIT branding.
- All-in-one dark-mode console, with optional pop-out panels for multi-monitor setups.
- Simulated inbound 911 calls, evolving incidents and scenario variation between sessions.
- AI-generated caller conversations and officer/fire/EMS radio responses.
- Microphone push-to-talk for dispatchers to address units and receive responses.
- Motorola-style channel selection, talkgroups, status controls and detachable radio console (design reference only; no manufacturer affiliation).
- CAD event intake, incident assignment, unit status and map-based resource tracking.
- Police, fire, EMS and utility response coordination.
- Voice strategy: reliable synthesized speech with prerecorded or browser fallback, plus explicit playback diagnostics and replay support.
- Default session requirement: start with one queued call; rotate scenarios across fresh sessions.
- Editable console position labels and administrator-managed settings.
- Future commercial options: limited trial/demo and subscription licensing.

These are **product requirements and development targets**, not a claim that every feature has been implemented or tested.

## Proposed infrastructure

- Cloudflare Workers for app and service endpoints.
- Cloudflare Workers AI for simulated callers, radio dialogue and voice where supported.
- Cloudflare D1 for incident, unit and session data where needed.
- Cloudflare KV/R2 for caching and stored assets where appropriate.
- Dedicated radio gateway for simulated communication routing.

Actual resource bindings, model IDs, deployment commands and usage costs must be validated against source code and the Cloudflare account. Free-tier operation is a goal, not a guarantee.

## Engineering priorities

1. Import the deployed source into this repository and document its actual dependencies.
2. Verify inbound call audio, two-way PTT, radio channel switching and AI responses.
3. Guarantee an audible fallback when AI voice generation is unavailable; test replay and refresh behavior.
4. Synchronize CAD incidents, unit statuses, map positions and radio traffic.
5. Validate single-screen usability, pop-outs, authentication and administrative settings.
6. Add reproducible builds, tests, CI and Cloudflare deployment configuration.
7. Implement trials/subscriptions only after core simulation and access control are verified.

## Safety and scope

This product is a **fictional emergency dispatch simulation**. It does not connect to real 911, PSAP, CAD/NCIC or emergency radio infrastructure and must not be used to request emergency assistance. Avoid routing real emergency calls or transmitting on public-safety frequencies.

## Development

No build or deploy commands are published yet because this repository does not currently contain a verified application source tree. Add source, a sanitized configuration template, dependency lockfile, test instructions and deployment procedures before enabling CI/CD.

**Branding:** Powered by CJIT  
**Principle:** Plan. Test. Deliver. Support.
