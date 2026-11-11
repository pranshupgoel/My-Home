# My-Home

A desktop app for managing a housing society's shared facilities (clubhouse, gym, pool and so on). Residents sign up, get approved by an admin, and book time slots. Admins manage residents, facilities and bookings.

Built with **Python (Tkinter)** and **MySQL**.

## Features

**Residents**
- Sign up for an account (requests wait for admin approval)
- Log in and browse the society's facilities
- Book a facility for a date within the coming week and a chosen time slot
- View and cancel their own bookings

**Admins**
- Approve or reject pending sign-up requests
- Add or remove facilities, each with a description
- View all bookings and cancel them
- View and remove residents

## Data model

| Table | Purpose |
|---|---|
| `residents` | Approved users, with unit number, contact details and an admin flag |
| `PendingApprovals` | Sign-up requests awaiting an admin decision |
| `facilities` | Bookable amenities and their descriptions |
| `bookings` | Facility, resident, date and time slot |

## Project layout

| File | Role |
|---|---|
| `db.py` | Creates the `MyHome` database and its tables (run once) |
| `value.py` | Seeds demo residents, an admin account and sample data |
| `main.py` | Entry point: login and sign-up windows |
| `resident.py` | Resident screens: bookings and new booking |
| `admin.py` | Admin screens: approvals, facilities, bookings, residents |

## Running it

Requires Python 3 and a local MySQL server (default `root` user, empty password; change it in the connection lines if yours differs).

```bash
pip install -r requirements.txt
python db.py      # once: create the database and tables
python value.py   # optional: load demo data
python main.py
```

## Notes

This was built as a learning project, so it is meant for local use only. Passwords are stored in plain text and the database credentials are hard-coded; a production version would hash passwords, use parameterised queries and read credentials from the environment.
