# CampusNest — Feature Specification & Project Roadmap

## 1. Project Overview
**CampusNest** is a centralized campus and hostel booking management web application. It simplifies how students view, reserve, and manage campus facilities—such as hostel rooms, computer/science laboratories, seminar halls, and sports courts—while giving administrators full visibility and control over booking approvals, scheduling, and facility utilization.

---

## 2. Problem Statement
In many colleges and universities, reserving campus facilities is still handled manually through paper forms, scattered emails, or informal messaging channels. This creates significant operational challenges:
- **Double-Bookings & Scheduling Conflicts:** Multiple groups attempting to use the same venue at the same time.
- **Lack of Visibility:** Students cannot see real-time availability of rooms or equipment without visiting administrative offices.
- **Slow Approval Cycles:** Requests get lost in physical inboxes or buried email threads, causing delays and uncertainty.
- **No Booking History:** Neither students nor administrators have an organized digital trail of who used which resource and when.

**CampusNest** solves this by providing a unified digital portal with real-time slot visibility, structured booking requests, conflict prevention, and streamlined administrator approvals.

---

## 3. User Roles & Permissions

### A. Student (Regular User)
- Register an account and log in securely.
- Browse, search, and filter bookable campus resources by category.
- View real-time availability using a calendar or time-slot picker.
- Submit booking requests with a defined purpose and requested time.
- Track booking statuses in real time.
- View full personal booking history on the "My Bookings" page.
- Cancel upcoming bookings when no longer needed.
- Receive automated email notifications for booking status updates.

### B. Admin (Facility / Campus Manager)
- Log in to a dedicated administrative dashboard.
- View all pending, active, and historical student booking requests in one place.
- Review student booking details, purpose, and requested time slots.
- Approve or reject booking requests with administrative remarks.
- Monitor facility usage schedules to prevent conflicts and maintain order.

---

## 4. MVP Features (10 Core Features)

These 10 core features establish the foundational system for both students and administrators:

1. **User Authentication for Students and Admins:** Secure registration and login mechanism with role-based access control (Student vs. Admin).
2. **Resource Listing with Details:** Browse all available campus facilities (hostel rooms, labs, seminar halls, sports courts) with key info such as capacity, location, amenities, and photos.
3. **Search and Filter Resources:** Keyword search across facility names, descriptions, and locations to quickly locate specific venues.
4. **Resource Category Filtering:** Quick filtering tabs or dropdowns to narrow resources by type (e.g., Hostel Rooms, Computer Labs, Seminar Halls, Sports Courts).
5. **Calendar or Time-Slot Picker:** Intuitive visual interface displaying available and unavailable slots for any selected date.
6. **Booking Request with Purpose and Time:** Dedicated submission form capturing event purpose, required date, and exact start/end time.
7. **My Bookings Page with Cancellation:** Personal student dashboard listing active and upcoming bookings, with a one-click option to cancel reservations.
8. **Booking Status Tracking:** Real-time visibility into the lifecycle state of each request (`Pending`, `Approved`, `Rejected`, `Cancelled`).
9. **Student Booking History:** Comprehensive log of all past bookings (completed, rejected, or cancelled) for personal records and auditing.
10. **Admin Dashboard to View Pending Requests:** Dedicated administrative view allowing admins to monitor incoming booking requests, inspect student details, and review requested slots.

---

## 5. Heavy Features (Days 11–12)

These 4 high-impact, advanced features require complex algorithmic checks, transactional database locking, and external service integration:

1. **Prevent Double Bookings:** Strict database-level constraints and transactional locks ensuring no resource can be booked twice for identical time periods.
2. **Prevent Overlapping Time Slots:** Robust collision detection logic to catch partial or full time overlaps before a booking request is accepted.
3. **Advanced Admin Approve/Reject Workflow:** Interactive decision controls allowing admins to approve or reject requests with custom feedback/rejection reasons, conflict verification, and state transitions.
4. **Automated Email Notifications:** Transactional email triggers that immediately alert students when their booking is submitted, approved, rejected, or cancelled.

---

## 6. Later Features (Post-MVP / Stretch Goals)

Features intentionally deferred to post-MVP development:
- **Recurring Bookings:** Reserve venues on a recurring weekly/monthly schedule (e.g., club meetings).
- **QR Code Check-in Verification:** Generate digital passes for verified entry at the venue.
- **Resource Maintenance Windows:** Admin capability to block dates for scheduled facility maintenance or repairs.
- **Departmental Access Restrictions:** Restrict specialized labs or executive halls to specific student cohorts.
- **Utilization Analytics & Reporting:** Graphical dashboard showing peak usage hours, resource popularity, and cancellation statistics.

---

## 7. Technology Stack

| Layer | Technology | Role & Why Chosen |
|-------|------------|-------------------|
| **Frontend** | **React** | Component-driven UI architecture; ideal for creating interactive calendars, slot pickers, and responsive dashboards. |
| **Backend** | **Python FastAPI** | Modern, fast, and beginner-friendly Python web framework with built-in data validation (Pydantic) and automatic interactive API documentation (`/docs`). |
| **Database** | **PostgreSQL** | Robust, ACID-compliant relational database essential for strict data integrity and preventing overlapping/double bookings. |
