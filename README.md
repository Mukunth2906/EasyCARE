# EasyCARE

> **Note:** This repository is an educational course project and portfolio prototype for demonstration purposes. It is not HIPAA/GDPR certified and is not intended for production healthcare use or storing real patient medical data.

**Live Frontend:** [https://easy-care-app.vercel.app](https://easy-care-app.vercel.app)

EasyCARE is a full-featured web application that bridges the gap between patients and healthcare providers. It offers seamless appointment scheduling, personal health data tracking, user profile management, and in-app notifications—enabling proactive, coordinated long-term care.

---

## Project Overview

EasyCARE simplifies healthcare management for both patients and doctors.

- **Patients:** Log health metrics, view visual health trends, book telemedicine appointments, and virtually consult doctors.
- **Doctors:** Manage schedules and appointment requests, conduct video consultations, and monitor submitted health data.

---

## Features

### User Authentication & Security
- Secure registration (with patient/doctor role selection) and login using **PyJWT** for access tokens and **Werkzeug** for salted password hashing.

### Role-Based Dashboards
- Tailored interfaces and functionalities for patients and doctors.

### Doctor Tools
- **Scheduling:** Create, view, edit, and delete available telemedicine time slots.
- **Appointment Management:** Review and accept/decline patient appointment requests.
- **Patient Roster:** Access list of patients with confirmed appointments.
- **Patient Health Overview:** Review historical biometric trends and vital charts.
- **Prescription Management:** Issue and manage digital prescriptions.
- **Virtual Consultation:** Conduct real-time video/audio consultations powered by **Twilio Video**.

### Patient Tools
- **Doctor Discovery & Booking:** Browse doctors, view real-time availability, and request appointments.
- **Appointment Tracking:** Receive instant notifications on appointment status updates.
- **Health Data Logging:** Track key metrics (Heart Rate, Glucose, SpO2, Temperature, Respiratory Rate) with threshold validation.
- **Health Data Visualization:** Interactive health history graphs powered by Chart.js.
- **Virtual Consultation:** Join confirmed video appointments directly from the browser.
- **Prescription Access:** View issued doctor prescriptions.
- **Pharmacy Redirect:** Quick access to integrated online pharmacies.

### Profile Management
- Comprehensive profile completion for patients and doctors.

### In-App Notification System
- Real-time in-app notifications for appointment confirmations and cancellations.

---

## Tech Stack

### Backend
- **Python 3.9+** & **FastAPI**
- **SQLAlchemy** (ORM) & **SQLite** (Development database)
- **Pydantic v2** (Data modeling & schema validation)
- **PyJWT** (Role-based JWT access token generation and validation)
- **Werkzeug** (Secure password hashing and verification via `generate_password_hash`)
- **Twilio Video:** FastAPI securely mints Twilio Video Access Tokens with `VideoGrant` on demand for confirmed appointments, validating participant authorization and appointment time windows.
- **Uvicorn** (ASGI server)

### Frontend
- HTML5, CSS3, Vanilla JavaScript
- **Chart.js** (Biometric charts & data visualization)
- **Font Awesome** (UI icons)

### Cloud & Deployment
- **Frontend:** [Vercel](https://easy-care-app.vercel.app)
- **Backend:** Render
- **Version Control:** Git & GitHub

---

## Getting Started (Local Setup)

```bash
git clone https://github.com/Mukunth2906/EasyCARE.git && cd EasyCARE
python -m venv venv && source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r backend/requirements.txt
cp backend/.env.example backend/.env  # Set SECRET_KEY and Twilio variables in backend/.env
cd backend && uvicorn main:app --reload
```

---

## Key Workflows

| Action                      | Navigation                                   |
|-----------------------------|----------------------------------------------|
| Doctor sets schedule        | Dashboard → "My Schedule" → Add/Save slots   |
| Patient books appointment   | Telemedicine → Choose Doctor → Select slot   |
| Doctor manages appointments | "My Appointments" → Accept/Decline           |
| Patient views appointment   | Notifications (Bell icon)                    |
| Video Consultation          | Confirmed appointment → Join Video Room      |
| Health Data Logging         | "Health Monitor" → Log/View charts           |
| Update Profile              | Profile → Edit & Save                        |

---

## Deployment Overview

- **Frontend Live URL:** [https://easy-care-app.vercel.app](https://easy-care-app.vercel.app) (Deployed on Vercel)
- **Backend API:** Deployed on Render
- **Database:** SQLite (local/dev) / configurable via `DATABASE_URL`
- **CORS:** Configured to allow requests from the deployed frontend origin.

---

## Summary

EasyCARE is a role-based telemedicine platform developed to enhance remote patient care and enable doctors to deliver streamlined, personalized services. With features like secure portals, real-time consultations, health tracking, appointment management, and health data visualizations, EasyCARE focuses on making virtual healthcare simple and accessible.

---

