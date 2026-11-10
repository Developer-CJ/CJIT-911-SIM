# Deployed Cloudflare Worker snapshot — Metrocoms 911

Source: the live `cjit-911-radio-ai` Worker, inspected November 10, 2026 (UTC). This repository tracks a deployed snapshot; the worker may change in Cloudflare between repository updates.

## Included in `deploy/worker.js`

- Metrocoms browser console with call taking, CAD/incident management, radio/PTT, unit-map workflows, and multi-monitor controls.
- Administrator configuration page, including ATC-branded administration served by the shared Worker where configured.
- Cloudflare Workers AI radio/caller/incident responses, speech/voice endpoints, and configurable audio assets.
- Integrated Scenario Command: simulated medical, fire, traffic, utility, flooding and hazardous incidents, decision-driven phases and D1 event history.
- Browser-native Basic Authentication protecting the main Metrocoms and administration hostnames; passwords remain Worker secrets, not source code.

## Project URLs

- Main simulator: https://911.cjitnetworks.com
- Administrator: https://admin.911.cjitnetworks.com
- Radio gateway: https://radio.911.cjitservices.tech
- AI radio gateway: https://radio.ai.911.cjitnetworks.com

## Dependencies and limitations

Cloudflare bindings required by the Worker: Workers AI, D1, and the configured R2 audio buckets. Authentication secrets are set separately from source. Database schema and deployment metadata are managed outside this snapshot; don't deploy this file to a fresh account without checking them.

The Scenario Command backend was tested in production through create, dispatch, arrival, stabilization and resolution, with Workers AI dialogue and D1 event persistence. This does **not** verify every UI interaction, microphone permission, live audio playback or the complete AI voice → synthesized TTS → prerecorded fallback chain. Those still require client-device testing.

This source is intentionally public under the repository's existing GPL v3 license, as approved by the repository owner. Do not commit actual credentials, session tokens, private account IDs, network topology exports, customer data, or audio files you don't have permission to redistribute.

**Powered By CJIT · Plan. Test. Deliver. Support.**
