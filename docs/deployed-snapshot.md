# Deployed Cloudflare Worker snapshot — Metrocoms 911

Snapshot date: 2026-11-10 (UTC). Source: active Cloudflare Worker `cjit-911-radio-ai`; production deployment version `58502ad0-bf56-4eed-8f94-4d78b6518428` at inspection.

## Files

- `deploy/worker.js` — preserved Worker script from Cloudflare, including 911 console, admin console, AI radio and voice service routes, and ATC administration hostname branding correction.

## Production hostnames

- `911.cjitnetworks.com` — Metrocoms main browser simulator.
- `admin.911.cjitnetworks.com` — Metrocoms administration.
- `admin.atc.cjitnetworks.com` — ATC-branded administration served by this shared backend.
- `radio.911.cjitservices.tech` — radio/AI gateway.
- `radio.ai.911.cjitnetworks.com` — AI radio gateway.

## Required Cloudflare bindings (no values included)

- `AI` (Workers AI)
- `DB` (D1; configure the production database in Cloudflare)
- `AUDIO`, `ATC_AUDIO` (R2 buckets)

## Status and caveats

This is a **deployment-source snapshot**, not a promise that every UI, voice reply, microphone, sound asset, fallback, subscription or account flow is fully implemented and verified. The admin branding update is present in the worker code. HTTP status and page identity have been checked; end-to-end audio and interaction tests remain necessary.

The deployed Worker currently has voice usage limits and a separate administrator login. Never commit real passwords, tokens, database exports or account secrets. Keep this public repository free of customer information and infrastructure credentials. Before redeploying, review the Worker settings and preserve existing bindings to avoid downtime.
