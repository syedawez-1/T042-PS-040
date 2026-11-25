# Cinema and Event Ticketing System with Seat Holds and Dynamic Pricing

## 1. Project Overview

The Cinema and Event Ticketing System is a Python-based backend application designed to manage cinema ticket reservations, temporary seat holds, dynamic ticket pricing, loyalty rewards, and booking cancellations.

The system uses SQLite for database management and processes ticketing operations according to predefined business rules.

## 2. Problem Statement

**T042 – PS-040: Cinema and Event Ticketing with Seat Holds and Dynamic Pricing**

The objective is to develop a ticketing backend that supports temporary seat reservations, prevents double booking, calculates dynamic ticket prices, manages loyalty points, and handles cancellations and refunds.

## 3. Technologies Used

- Programming Language: Python
- Database: SQLite
- Testing: Pytest
- Version Control: Git and GitHub
- Development Environment: Visual Studio Code

## 4. Main Features

- Temporary seat holds with an 8-minute expiry.
- Automatic release of expired seat holds.
- Prevention of duplicate seat reservations.
- Contiguous seat selection and single-seat gap validation.
- Dynamic pricing based on seat occupancy.
- Opening-day and last-two-hour pricing adjustments.
- Group booking and weekday matinee discounts.
- GST and convenience fee calculations.
- Loyalty points earning and redemption.
- Booking cancellation and refund calculations.
- Age verification for A-rated movies.
- Seat availability and booking reports.

## 5. Business Rules

The system implements the following business rules:

1. Seat holds are limited to 10 seats per user per show and expire after 8 minutes.
2. A user can have only one active hold per show.
3. Seat selection must follow the specified contiguous seating and single-gap rules.
4. Dynamic pricing depends on occupancy:
   - Below 50%: 1.0x
   - 50% to below 80%: 1.15x
   - 80% and above: 1.3x
5. Opening-day pricing takes priority over the last-two-hour discount.
6. Convenience fees and GST are calculated according to ticket quantity and price.
7. Group booking and matinee discounts do not stack.
8. Weekday matinee discounts apply to eligible CLASSIC and PRIME tickets.
9. Loyalty points can be earned and redeemed according to the specified limits.
10. Cancellation refunds depend on the time remaining before the show.
11. A-rated movies require all ticket holders to be at least 18 years old.
12. Eligible RECLINER seat re-holds preserve the original frozen occupancy pricing.

## 6. Project Structure

```text
T042-PS-040/
│
├── database/
│   ├── db.py
│   ├── schema.sql
│   ├── seed_data.py
│   └── import_official_data.py
│
├── data/
│   └── T042-PS-040-sample-data/
│
├── docs/
│   ├── business_rules.md
│   ├── decision_log.md
│   └── design_document.md
│
├── models/
│
├── services/
│   ├── booking_service.py
│   ├── cancellation_service.py
│   ├── command_processor.py
│   ├── loyalty_service.py
│   ├── pricing_service.py
│   ├── report_service.py
│   └── seat_service.py
│
├── tests/
│   ├── test_booking.py
│   ├── test_br02.py
│   ├── test_cancellation.py
│   ├── test_edge_cases.py
│   ├── test_pricing.py
│   └── test_seats.py
│
├── output/
│   ├── booking_events.csv
│   ├── seat_maps.csv
│   └── ticket_lines.csv
│
├── main.py
├── config.py
├── requirements.txt
├── README.md
└── .gitignore
```

## 7. Installation

Clone the repository:

```bash
git clone https://github.com/sushmaspalled-hash/T042-PS-040.git
```

Navigate to the project directory:

```bash
cd T042-PS-040
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate the virtual environment on Windows:

```powershell
venv\Scripts\Activate.ps1
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

## 8. Database

The project uses SQLite to store cinema information and ticketing data.

The official sample dataset includes:

- Venues
- Screens
- Seats
- Movies
- Shows
- Users
- Presold seats

The database is populated using the official sample dataset supplied for the problem statement.

## 9. Testing

Run the test suite using:

```bash
pytest -v
```

### Latest Test Results

- Total tests: 26
- Passed: 26
- Failed: 0

All 26 tests passed successfully during the latest test run.

## 10. Generated Output Files

The system generates the following CSV reports:

| File | Description |
|---|---|
| ticket_lines.csv | Ticket pricing, discounts, GST and totals |
| booking_events.csv | Booking events, results and refunds |
| seat_maps.csv | Seat availability and reservation status |

## 11. Team Information

**Team ID:** T042

**Problem Statement:** PS-040

**Project Title:** Cinema and Event Ticketing with Seat Holds and Dynamic Pricing

**Team Members:**
- Sushma Sharanappa Palled
- Syed Mehmood Awez

## 12. Repository

GitHub Repository:

https://github.com/sushmaspalled-hash/T042-PS-040

---

**Project Status:** Core implementation and initial test suite completed. Final validation and documentation review are in progress.

## 13. Project Status

Core backend implementation completed.

- Seat hold and booking management implemented.
- Dynamic pricing and discount calculations implemented.
- Loyalty points and cancellation/refund handling implemented.
- SQLite database integration completed.
- CSV reports generated successfully.
- 26 automated tests passed.
- Latest changes committed and pushed to GitHub.

The project is ready for final integration and demonstration.


## 14. System Workflow

The application follows this workflow:

1. User interacts with the application menu.
2. Command Processor receives the user's request.
3. Business logic services process the request.
4. Seat Service manages seat availability and holds.
5. Booking Service handles booking confirmation.
6. Pricing Service calculates ticket prices and discounts.
7. Loyalty Service manages reward points.
8. Cancellation Service processes cancellations and refunds.
9. SQLite stores the application data.
10. CSV reports are generated for ticket lines, booking events and seat maps.

### Architecture

User
  |
  v
Interactive Menu
  |
  v
Command Processor
  |
  v
Business Logic Services
  |
  +-- Seat Service
  +-- Booking Service
  +-- Pricing Service
  +-- Loyalty Service
  +-- Cancellation Service
  |
  v
SQLite Database
  |
  v
CSV Reports

## 15. Future Enhancements

The following features can be considered for future development:

- Web-based user interface.
- Online payment gateway integration.
- Admin dashboard.
- Email and SMS booking confirmations.
- Real-time seat availability.
- Enhanced booking analytics.
## 16. DEMO VIDEO
 - https://drive.google.com/file/d/1KNx4-0m_aNvvTelJnPyMq5aYb1XaWfKV/view?usp=sharing
