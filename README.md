# The Grab Standard — STA Tracking Screen Prototype

The interactive hero execution for **The Grab Standard**, a student campaign entry for the **Kancil Awards** (CO5 · Best Idea for Social Good). This is the customer's live delivery-tracking screen, rebuilt around **STA — Safe Time of Arrival** and the **Rider Risk Score (RRS)** safety engine.

**Live prototype:** https://sta-prototype-grabfood-kancil.vercel.app

---

## What this is

Malaysia loses close to one food-delivery rider a week on the road. A big part of the pressure is the delivery clock: when the ETA slips and the app never says why, customers blame the rider, and to protect his rating he speeds to win back minutes that were never his fault.

STA replaces that clock. Underneath it runs a live safety engine — the **Rider Risk Score** — which reads rain, traffic, road risk and how the rider is actually riding, and scores his danger second by second. When risk climbs, Grab adds **Safe Minutes** to the customer's window and shields the rider's rating and pay, so he is never forced to speed. Danger up, pressure off.

This prototype demonstrates that idea as a working screen:

- **One honest clock** — a fixed "Arriving Safely by" time that never silently moves.
- **One visible journey** — a four-stop progress bar (Order · Kitchen · Road · Home) the customer follows in real time.
- **One fair review** — app, merchant and rider rated separately, so blame is routed to its true owner.
- **The RRS dial** — a live Rider Risk Score gauge (green → amber → red) that makes the safety engine visible, and whose rise is what causes the Safe Minutes to appear.

---

## How to view it

**Online:** open the live link above on a phone.

**Locally:** download the repo and open `index.html` in any modern browser. There is no build step and no server required — it is a single self-contained file.

### Demo controls
- Tap any **chip** at the top to jump to a specific moment (Processing → Fair review).
- Tap **▶ Play journey** to auto-run the full delivery from order to review.
- Open the **Fair review** state to test the three-party rating (all three rows are interactive).

### URL parameters
| Parameter | Effect |
|-----------|--------|
| `?embed` | Full-bleed phone only — hides the surrounding board, chips and captions. Also triggers automatically when embedded in an iframe. |
| `?autoplay` | Auto-plays the journey on load. |
| `?static` | Freezes all motion and shows the hero weather state (useful for screenshots / print). |

Example: `…vercel.app/?embed&autoplay`

---

## Deploying (GitHub → Vercel)

The production file **must be named `index.html`** so it serves at the root URL.

1. Push `index.html` to this repository.
2. In Vercel: **Add New → Project → Import** this repo.
3. Framework preset: **Other**. No build command, no settings needed.
4. **Deploy.** Every subsequent push auto-redeploys.

The public URL is derived from the Vercel **project name**, so keeping the project named `sta-prototype-grabfood-kancil` preserves the link encoded in the campaign QR code.

---

## Tech notes

- Single self-contained `index.html` — HTML, CSS and vanilla JavaScript, no frameworks or build tooling.
- Only external asset is the Inter web font (loaded from Google Fonts).
- Fully responsive; respects `prefers-reduced-motion` and includes `static` / `embed` modes for capture and presentation.
- The RRS colour zones (0–59 green · 60–79 amber · 80–100 red) reuse the on-screen traffic-light hues and interpolate smoothly between states.

---

## Campaign

**Category:** CO5 — Best Idea for Social Good · **Client:** Grab (GrabFood)
**Concept:** STA (Safe Time of Arrival) + the Rider Risk Score engine, published openly as *The Grab Standard*.

**Team**
- Daniel Phua Chu Yuan — 26014464
- Careen Tan Ying Sze — 24032385
- Liong Xin Yu — 24027617

---

*Prototype for academic / awards submission. Grab, GrabFood and related marks belong to their respective owners; this is a non-commercial student concept.*
