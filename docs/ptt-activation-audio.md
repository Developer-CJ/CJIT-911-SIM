# Metrocoms PTT activation audio

The Metrocoms 911 Simulator uses the approved `mic-ptt.mp3` for the `ptt_on` audio event. This event is triggered when the radio or simulated phone PTT is engaged.

- Filename: `mic-ptt.mp3`
- Format: MP3 (`audio/mpeg`), 4,431 bytes
- Event: `ptt_on` (radio and phone)
- Volume: 85%
- Runtime: Cloudflare Worker `cjit-911-radio-ai`
- Storage: Cloudflare R2 bucket `cjit-metrocoms-audio`, object `sounds/03e3ef3d-bbc0-4d0a-a8cf-8edc405eaa77`
- Configuration: D1 `metrocoms_audio_config` key `main`, `sounds.ptt_on` = `{"asset":"03e3ef3d-bbc0-4d0a-a8cf-8edc405eaa77","volume":85,"enabled":true}`

This is a reference to the *already configured* production sound, not a deployment script. Audio assets are administered through the existing simulator audio administration UI. Do not overwrite the newer production Worker with the older `deploy/worker.js` repository snapshot.

**Verification:** The asset was previously checked in R2 (MP3 ID3 header and 4,431 bytes), and its D1 configuration was read back successfully. Actual speaker/headset playback still needs browser/device testing. This document does not assert that the repository snapshot matches production.