# technova2025-binary_duo
Project name:- MEDIC – Unified Digital Healthcare Platform

Problem statement
The core problem solved by the "Medic" platform is the current fragmentation and inefficiency in accessing essential healthcare services, which often involves navigating multiple, isolated systems for bookings, consultations, records, and information. Medic addresses this by creating a single, unified digital hub across web, mobile, and AI, thereby simplifying the user journey, accelerating service access, and centralizing all medical interactions and data to create a more streamlined and cohesive healthcare experience.


How it works
# 📘 MEDIC — Project Documentation
A tele‑health platform with patient, doctor & admin modules.

---

# 1. System Overview

MEDIC provides:
- Patient Login
- Doctor Login
- Admin Login
- Appointments
- QR Emergency Medical Profile
- AI Symptom Checker
- Medical Records System
- SOS Alerts
- Video Consultation (placeholder)

---

# 2. How The System Works

## 2.1 Role-Based Login
Database `users` table includes:
- name
- email
- password
- role (patient / doctor / admin)

User enters credentials → backend verifies → redirects:

- Patient → dashboard.html  
- Doctor → doctor_dashboard.html  
- Admin → admin_dashboard.html  

Session stored in `localStorage`.

---

## 2.2 Appointments System

### Patient:
1. Fills appointment form  
2. Calls `appointments/create.php`  
3. Stored in DB  
4. Listed in dashboard  

### Doctor:
- Sees all appointments  
- Can update status (pending → approved → completed)

### Admin:
- Sees all appointments with patient + doctor names

---

## 2.3 QR Medical Profile (Emergency)

1. Patient clicks “Generate QR”
2. Frontend → `qr/generate.php`
3. Backend:
   - Creates unique token
   - Stores token in `qr_profiles`
   - Generates QR using Google Charts API
4. When scanned:
   - Opens `qr/get_profile.php?token=XYZ`
   - Displays name, phone, blood group, allergies

Used for emergencies.

---

## 2.4 Medical Records System

Patients can:
- Add new medical record
- Edit record
- Delete record
- View full history

Backend endpoints:
- POST `records/create.php`
- GET `records/list.php?user_id=X`
- GET `records/get.php?id=X`
- POST `records/update.php?id=X`
- POST `records/delete.php?id=X`

Admins & doctors can view patient records.

---

## 2.5 AI Symptom Checker

User enters symptoms →  
Frontend sends:

Backend processes and returns:
- Possible conditions
- Suggested care
- When to seek help

---

## 2.6 SOS Alert System

When user triggers SOS:
- Device GPS is collected
- Frontend calls `emergency/sos.php`
- Data saved:
  - user_id
  - lat
  - lng
  - timestamp

Admin can view alerts.

---

## 2.7 Video Consultation (Placeholder)
Frontend → `video/create_session.php`  
Returns:
- `room name`
- `join URL`

Used for simulated video calling.

---

# 3. Installation & Setup Guide

## 3.1 Requirements
- XAMPP/MAMP  
- PHP 8+  
- MySQL  
- Browser  
- Internet (for QR API)

---

## 3.2 Project Folder Structure

Place entire project inside:

---

## 3.3 Database Setup

1. Go to phpMyAdmin  
2. Create DB:

3. Create tables:
- users
- appointments
- records
- qr_profiles
- sos_alerts

(You can export/import SQL)

---

Tech stack used are as follow

Frontend:- HTML, CSS, PHP.
Backend:- MYSQL.
Development Tool:- VS Code.

Setup instructions (how to run it)

http://localhost/medic_builder/medic_project/backend/
http://localhost/medic_builder/medic_project/frontend/index.html


Team member names:-
Divyesh Gohil,
Jigar Rupareliya 

PPT
[Presentation - Unified Digital Healthcare Platform.pdf](https://github.com/user-attachments/files/23688616/Presentation.-.Unified.Digital.Healthcare.Platform.pdf)
