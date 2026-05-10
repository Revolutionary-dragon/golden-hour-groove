# 🎟️ Golden Hour Groove — Event Ticketing System

> A full self-service event ticketing web app built for a live rooftop event in Nairobi, Kenya. No third-party ticketing platforms. Built from scratch with vanilla JavaScript, Firebase Realtime Database, and deployed on GitHub Pages.

🔗 **Live Site:** [revolutionary-dragon.github.io/golden-hour-groove](https://revolutionary-dragon.github.io/golden-hour-groove)

---

## 📸 Overview

Golden Hour Groove is a real-world ticketing system built for a rooftop music event headlined by **Prod Muuo** on **1st May 2026** at **Tsavo Royal Suburbs Phase 2, Nairobi**.

The system handles the full ticketing lifecycle — from buyer purchase to door check-in — without relying on any paid ticketing service.

---

## ✨ Features

### Buyer Side
- Animated event landing page with golden hour aesthetic
- 3-step ticket purchase flow (details → M-Pesa payment → reference submission)
- Real-time submission to Firebase database
- Instant booking confirmation with reference code

### Organizer Dashboard
- Password-protected organizer access
- Live attendee list synced from Firebase in real time
- Pending / Confirmed / Checked-In status tracking
- One-click ticket generation with unique QR code per attendee
- **Send via WhatsApp** button — opens WhatsApp with buyer's number and ticket details pre-filled
- Door check-in mode — verify ticket codes at the entrance instantly

### Ticket
- Branded ticket design with event details
- Unique ticket code (GHG-001, GHG-002...)
- QR code encoding attendee name, code, and ticket type
- Nairobi skyline silhouette and golden hour visual theme

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla HTML, CSS, JavaScript |
| Database | Firebase Realtime Database |
| QR Generation | QRCode.js |
| Fonts | Google Fonts (Bebas Neue, DM Sans, Playfair Display, DM Mono) |
| Hosting | GitHub Pages |
| Payment | M-Pesa (manual verification flow) |

---

## 🏗️ Architecture

```
Buyer (any device)
    │
    ▼
index.html (GitHub Pages)
    │
    ├── Submits form → Firebase Realtime Database
    │
Organizer (any device)
    │
    ▼
index.html → Organizer Tab (password protected)
    │
    ├── Reads live from Firebase
    ├── Confirms payment manually
    ├── Generates ticket + QR code
    └── Sends via WhatsApp deeplink
```

---

## 💳 Payment Flow

This system uses **M-Pesa** — Kenya's dominant mobile money platform — for payments:

1. Buyer enters their details on the site
2. Site displays the organizer's M-Pesa number and exact amount (KES 500)
3. Buyer sends payment via M-Pesa and copies the reference code from their SMS
4. Buyer submits the reference code — request goes to Firebase
5. Organizer verifies payment on their phone, confirms on dashboard
6. Ticket + QR code generated, sent to buyer via WhatsApp

---

## 🚀 How to Run Locally

1. Clone the repo:
```bash
git clone https://github.com/Revolutionary-dragon/golden-hour-groove.git
```

2. Open `index.html` in your browser — no build step needed.

3. To connect your own Firebase database, replace the config in the `<script type="module">` block at the bottom of `index.html` with your own Firebase project credentials.

---

## 🔐 Security

- Organizer dashboard is password protected (client-side)
- Firebase database rules set to allow read/write during event period
- For production use, Firebase rules should be tightened with proper authentication

---

## 📁 Project Structure

```
golden-hour-groove/
├── index.html        # Full single-file application
└── README.md         # Project documentation
```

---

## 👨‍💻 Built By

**Marvelle** — 2nd Year BSc Data Science student at KCA University, Nairobi.  
Aspiring quant finance professional with a passion for building real-world projects.

---

## 📄 License

MIT License — free to use and adapt.
