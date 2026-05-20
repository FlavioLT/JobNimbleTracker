# 📍 JobNimble Tracker

A lightweight, browser-based GPS tracking tool for field service teams. Managers see a live map of all active Service Members. Employees clock in and out directly from their phone — no app install required.

---

## 🔗 Live Demo

| Page | URL |
|------|-----|
| Manager Dashboard | https://flaviolt.github.io/JobNimbleTracker/dashboard.html |
| Service Member Page | https://flaviolt.github.io/JobNimbleTracker/worker.html |

---

## ✨ Features

**Manager Dashboard**
- Live map of Florida with color-coded pins per Service Member
- Real-time Active / On Lunch / Total counters
- Sidebar with search bar to quickly find any Service Member
- Click any pin or card to zoom in and view details (status, GPS accuracy, last update)
- Status badges: Active 🟢 / On Lunch 🟡 / Off Duty ⚫
- Remove inactive Service Members with one click
- Day/Night map toggle (☀️/🌙) in the top right
- 5 color themes via the ⚙️ settings panel

**Service Member Page**
- Clock In / Go to Lunch / Off Lunch / Clock Out flow
- GPS updates every 5 minutes while clocked in
- One location snapshot taken at lunch start and one on return
- Today's session log with timestamps and total hours worked
- 5 color themes + day/night mood toggle
- Works directly in a phone browser — no app install needed

---

## 🛠 Tech Stack

| Tool | Purpose |
|------|---------|
| [Firebase Realtime Database](https://firebase.google.com/) | Real-time location sync between devices |
| [Leaflet.js](https://leafletjs.com/) | Interactive map rendering |
| [CartoDB / OpenStreetMap](https://carto.com/) | Map tile layers (dark + voyager) |
| [GitHub Pages](https://pages.github.com/) | Free static hosting |

No backend server required. No monthly infrastructure costs at this scale.

---

## 🚀 How to Use

### Manager
1. Open the **Dashboard** URL in any browser
2. Service Members appear on the map automatically as they clock in
3. Use the search bar to find specific team members
4. Click a pin or sidebar card to view their details
5. Use 🗑 to remove Off Duty members who are no longer active

### Service Member
1. Open the **Worker** URL on your phone
2. Enter your name (or it can be pre-filled via URL: `worker.html?name=YourName`)
3. Tap **Clock In** and allow location permission
4. Use **Go to Lunch** / **Off Lunch** during your break
5. Tap **Clock Out** at the end of your shift
6. ⚠️ Keep the browser tab open — closing it stops GPS updates

---

## ⚠️ Current Limitations

This is a **prototype** built for testing and proof-of-concept only.

- Tracking stops if the phone screen locks or the tab is closed (browser limitation)
- No user authentication — anyone with the link can access the pages
- Names are entered manually — no employee database or admin panel yet
- No timesheet export or payroll integration yet
- Works best on **Chrome for Android** — iOS Safari may restrict background location

---

## 🔧 Setup & Configuration

If you want to run your own instance:

1. Create a free project at [firebase.google.com](https://firebase.google.com)
2. Enable **Realtime Database** in test mode
3. Register a web app and copy your Firebase config
4. Replace the `firebaseConfig` object in both `dashboard.html` and `worker.html`
5. Set your database rules to allow read/write:
```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```
6. Upload both HTML files to GitHub and enable GitHub Pages

---

## 🗺 Roadmap

- [ ] User login & authentication
- [ ] Admin panel for managing employees
- [ ] Timesheet export (PDF / CSV)
- [ ] Payroll integration (JobNimble API)
- [ ] Push notifications for manager alerts
- [ ] Native iOS & Android app (React Native) with background GPS every 5–10 seconds

---

## 📱 Path to a Native App

The core limitation of the browser version is that GPS stops when the screen locks. A native app built in **React Native** would solve this — continuous background tracking every 5–10 seconds, even with the screen off. The existing Firebase backend requires zero changes. Estimated timeline for a V1 native app: **4–8 weeks**.

---

## 👤 Author

Built by Flavio Teron  
[github.com/FlavioLT](https://github.com/FlavioLT)
