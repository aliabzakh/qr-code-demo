# Aramco Americas conference check-in prototype

Open `index.html` directly for the group, invite, QR rotation, and simulated scan flows.

For live camera scanning, serve the folder on localhost because browsers restrict camera access on ordinary file URLs:

```bash
cd qr-code-demo
python3 -m http.server 8765
```

Then open <http://localhost:8765> in a current Chromium-based browser.

## Included

- Leader group management, removal, and leadership transfer
- Immediate joining or optional leader approval
- Shareable invite-link flow
- Seven sample attendees across rotating sets of four
- Two-second QR set rotation with pause and manual controls
- AES-GCM-encrypted demo tokens; personal data is not visible in QR text
- Native multi-QR camera detection when `BarcodeDetector` is supported
- Photo scanning and a reliable four-pass scanner simulation
- Duplicate, event, expiry, and safety-acknowledgement checks
- NFC phone-tap product-flow simulation with invite-link fallback
- Local browser persistence with no backend

## Production requirements

The browser prototype uses a shared demonstration encryption key and local storage. A production deployment should use authenticated users, a backend group service, server-issued short-lived signed or encrypted tokens, audit logs, consent/privacy retention rules, and an approved Aramco brand package.

Cross-device invite updates require a backend or realtime service. Reliable phone-to-phone NFC also requires native mobile capabilities; the web experience should retain the link/QR fallback.
