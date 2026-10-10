# SentryLine

**Real-time scam-call risk detection and response — a browser-based prototype.**

SentryLine analyzes typed text, sample call transcripts, or browser speech-recognition output for common scam indicators. It is designed as a demonstration project for helping users recognize social-engineering patterns such as digital-arrest threats, fake bank KYC requests, OTP/PIN theft, and remote-access scams.

## Features

- Dark cybersecurity dashboard with a live risk gauge, score breakdown, timeline, and system log.
- English, Telugu, and Telugu-English scam phrase matching.
- Sample scenarios for digital-arrest, bank KYC, remote-access, UPI refund, and safer calls.
- Browser microphone input and speech-to-text where supported.
- Risk levels: **SAFE**, **SUSPICIOUS** (score 40+), and **CRITICAL SCAM** (score 70+).
- Guardian alert screen with a pairing link; cross-device notifications use the public ntfy.sh service.
- Optional siren, emergency contacts, Telegram alerts, and short evidence recording.
- Local browser storage for settings and incident history.

## Run locally

1. Download or clone this repository.
2. Open `index.html` in a modern browser.
3. For microphone access and some browser APIs, serve the file from localhost or HTTPS rather than opening it directly.

Example local server with Python:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## How to try it

1. Select a sample call scenario and click **Play sample call**, or type a sentence in the transcript input.
2. Review the risk score, matched indicators, and suggested response.
3. To test the guardian view, copy the guardian link and open it in another tab/device, then enable alarm sound and send a test alert.
4. Configure Telegram only if you want to test that optional integration.

## Technology

- HTML, CSS, and vanilla JavaScript
- Web Speech API (browser support varies)
- Web Audio API and Canvas for audio visualization and siren
- LocalStorage and IndexedDB for local settings and optional evidence
- BroadcastChannel for same-browser guardian alerts
- ntfy.sh for cross-device guardian notifications
- Telegram Bot API for optional message and evidence delivery

## Important limitations and safety

- This is a **prototype**, not a production call-interception system. A browser page cannot directly intercept ordinary cellular calls.
- Detection is based on keyword/rule scoring, not a trained machine-learning model. It can miss scams or flag legitimate conversations.
- Microphone access, speech recognition, notifications, background execution, and recording depend on browser/device permissions and support.
- Cross-device guardian alerts send data through ntfy.sh. Treat pairing codes as sensitive and do not use real personal or financial information during demos.
- Telegram bot tokens are sensitive credentials. Do not commit tokens or share them; use a test bot and rotate any token that has been exposed.
- Recording or sharing audio should be done only with appropriate consent and in accordance with applicable law.
- In India, report suspected cyber financial fraud through **1930** or the official portal at https://cybercrime.gov.in/.

## Project purpose

SentryLine is a hackathon/learning prototype exploring how real-time language cues and simple risk scoring could help people pause before sharing OTPs, UPI PINs, passwords, or transferring money under pressure.

## License

No license has been specified yet. Add a license before allowing reuse or redistribution.
