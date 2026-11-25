# CLAUDE.md — PMI God's Eye

Created by OPS' Broker

## Project

**PMI God's Eye** — the interactive member app of OMNI-PRESENT SOLUTIONS, INC carrying the God's Eye scholarship program: the scholarship application and program information (the school being built, the Academy, certification — people get certified and can certify others), the God's Eye / Excalibur test, a World View map, member-added videos, member-to-admin talk via HIIYAH, and a back office with separate member and administrator logins (administrator access for the owner). Owner: Honorable Jay Ladon Dickey Sr. EL.

Front domain: **pmigodseye.genesis**. Google Play package: `com.omnipresentsolutions.godseye`. Play target age starts at **13** (13–15, 16–17, 18+) — set by the owner's instruction; the other apps in this family are 18+.

## Tech in this folder

- `index.html` — the entire app: one self-contained HTML file (HTML/CSS/JavaScript inline, no build step, no framework, no server). Edit it directly.
- `privacy.html` — the hosted privacy policy page for the Play Store listing.
- `README.md` — project note. Keep it accurate when behavior changes.

There is no backend. Accounts, chat, videos, and applications run session-only in the browser unless this file says otherwise.

## The scholarship facts (do not change these numbers)

- Application fee: **$50 in Bitcoin** to take the God's Eye test — the Excalibur test.
- Scholarship: **$20,000**, awarded to people who can activate the device with their left or their right hand (the device does not work for everybody).
- The owner will supply the detailed Excalibur test text himself. Do not invent test content; build around the text he provides when it arrives.

## Standing rules (apply to every change)

- **Cross-platform, no exceptions:** must work on the owner's Samsung Galaxy S9 (SM-G960U), iPhones (Safari/WebKit), all other phones, and laptops/desktops. Responsive at every width.
- **Adjust to the device:** runtime feature detection and progressive enhancement — WebGL2 → WebGL1 → CSS fallback; camera features fall back gracefully; auto quality scaling; honor reduced-motion and low-power signals.
- **Lane separation:** God's Eye is its own lane. Member-to-admin talk is "via HIIYAH" by name; no Excalibur train material in here.
- **One-picture rule:** visuals blend into one seamless picture — matched lighting, perspective, color, shadows. Logos merge into the design with no visible outlines or background-box edges.
- **Cross-app sidebar:** every app in this family (Excalibur Line, FinSwap, HIIYAH, Dominion Network, PMI God's Eye) carries a sidebar linking to all the others. Keep it intact and uniform.
- **Credit:** the line "Created by OPS' Broker" / "Shared by OPS' Broker" stays in the files. Do not remove it, do not add any other creator name.
- **Honesty:** never present demo accounts, chat, videos, applications, or the fee payment as live server-backed functionality. Age-appropriateness matters here — the audience starts at 13.

## ⭐ REAL PAYMENTS — the $50 Bitcoin test fee

The scholarship test fee must be a **real Bitcoin transaction on the real Bitcoin blockchain**, not a simulated fee slip.

Current state: the fee slip routes through FinSwap and is demo-labeled. That is the thing to fix.

Required implementation:

1. The applicant pays **$50 worth of Bitcoin** (priced from a real BTC rate at the moment of payment) to the program's published Bitcoin address, built on the open-source Bitcoin stack (**Bitcoin Core + Counterparty**, the same stack FinSwap uses).
2. **The applicant pays from their own real wallet.** The app shows the address / payment request / QR; the applicant's wallet signs and broadcasts. Verify the payment on the real chain (amount + confirmations) before marking the fee paid and unlocking the test.
3. **Never hold, request, receive, store, or transmit a user's seed phrase or private key — server-side or anywhere else.** A public address is all the flow needs.
4. The wider accepted-asset family for this app family is Bitcoin, PERFECTCERTS, WEALTHTICKET, and Alpine Gold-backed currencies — but the test fee itself is specified by the owner as **$50 in Bitcoin**; keep it Bitcoin unless the owner changes it.
5. Until the fee path is connected and verified with a real (even tiny) transaction, keep it labeled demo; remove the label only when verified live.

## Working notes

- Test every change at phone width (Galaxy S9) and desktop width before calling it done, and check Safari/WebKit behavior for anything using newer APIs.
- Report only completed, verified results. An attempt is not a result.
