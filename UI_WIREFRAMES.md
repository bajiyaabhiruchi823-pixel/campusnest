# CampusNest — UI Wireframes & Design System Specification

## 1. Design System & Theme Foundations

CampusNest is designed with a **modern SaaS dashboard aesthetic**: clean, structured, data-dense without being cluttered, and accessible.

### Color Palette

| Token | Hex Code | Tailwind Equivalent | Usage |
|---|---|---|---|
| **Navy Deep** | `#0F172A` | `bg-slate-900` | Desktop sidebar background, dark surface accents |
| **Navy Muted** | `#1E293B` | `bg-slate-800` | Sidebar hover states, active menu item backgrounds |
| **Primary Blue** | `#2563EB` | `bg-blue-600` | Main CTA buttons, active tabs, brand accents, links |
| **Primary Blue Hover** | `#1D4ED8` | `bg-blue-700` | Primary button hover state |
| **Primary Blue Light** | `#EFF6FF` | `bg-blue-50` | Active selection backgrounds, subtle pill highlights |
| **Surface White** | `#FFFFFF` | `bg-white` | Main cards, modals, content panels |
| **Canvas Gray** | `#F8FAFC` | `bg-slate-50` | Main dashboard page background |
| **Border Gray** | `#E2E8F0` | `border-slate-200` | Card borders, dividers, form input borders |
| **Text Primary** | `#0F172A` | `text-slate-900` | Page titles, primary headings, card titles |
| **Text Muted** | `#64748B` | `text-slate-500` | Subtitles, labels, metadata, helper text |

#### Semantic Status Colors

| Status | Badge Background | Badge Text | Border | Meaning |
|---|---|---|---|---|
| **Pending** | `#FEF3C7` (`amber-100`) | `#92400E` (`amber-800`) | `#FCD34D` (`amber-300`) | Awaiting admin review |
| **Approved** | `#DCFCE7` (`emerald-100`) | `#166534` (`emerald-800`) | `#86EFAC` (`emerald-300`) | Confirmed reservation |
| **Rejected** | `#FEE2E2` (`rose-100`) | `#991B1B` (`rose-800`) | `#FCA5A5` (`rose-300`) | Declined by admin |
| **Cancelled** | `#F1F5F9` (`slate-100`) | `#475569` (`slate-600`) | `#CBD5E1` (`slate-300`) | Revoked by student |

---

### Typography & Component Styles

- **Font Family:** `Inter`, system `-apple-system`, `sans-serif`
- **Headings:**
  - Page Title: `text-2xl font-bold tracking-tight text-slate-900`
  - Section Heading: `text-lg font-semibold text-slate-800`
  - Card Title: `text-base font-medium text-slate-900`
- **Buttons:**
  - *Primary:* Blue background (`#2563EB`), white bold text, `rounded-lg`, subtle shadow, hover transitions.
  - *Secondary:* White background, border `#E2E8F0`, slate text, hover `bg-slate-50`.
  - *Danger:* Red text or light red pill for destructive actions like cancel/reject.
- **Cards:** White background, `rounded-xl`, border `border-slate-200`, shadow `shadow-xs hover:shadow-md transition-shadow`.

---

## 2. Global Navigation & Layout Shell

### Desktop Shell (Sidebar + Top Navigation)

```
+------------------------------------------------------------------------------------+
|  [Logo] CampusNest  |  [ Search campus resources... ]   (Bell) (Avatar: Sarah Doe v) |
+---------------------+--------------------------------------------------------------+
|  SIDEBAR (w-64)     |  PAGE HEADER: Title & Breadcrumbs             [Primary Action] |
|  Navy (#0F172A)     +--------------------------------------------------------------+
|                     |                                                              |
|  * Dashboard        |  MAIN CONTENT VIEWPORT                                       |
|  * Explore Venues   |  (bg-slate-50, overflow-y-auto, p-6 md:p-8)                    |
|  * My Bookings      |                                                              |
|  * Notifications    |                                                              |
|  * Profile          |                                                              |
|                     |                                                              |
|  -----------------  |                                                              |
|  [?] Help & Support |                                                              |
|  [->] Logout        |                                                              |
+---------------------+--------------------------------------------------------------+
```

### Mobile Shell (< 768px)
- **Top Navigation Bar:** Sticky top with hamburger menu toggle on the left, logo in center, and profile avatar on the right.
- **Drawer Menu:** Slides from left on tap containing the navigation links.
- **Bottom Bar (Optional shortcut):** Quick access tabs: `[Home]`, `[Explore]`, `[My Bookings]`, `[Profile]`.

---

## 3. Screen Layouts & Wireframes

---

### Screen 1: Student Login & Registration
*Purpose: Fast, distraction-free authentication for students with a quick toggle to admin mode.*

```
+-----------------------------------------------------------------------------+
|                                                                             |
|                           +-----------------------+                         |
|                           |   [Logo] CampusNest   |                         |
|                           |   Campus Facility     |                         |
|                           |   Booking Portal      |                         |
|                           +-----------------------+                         |
|                                                                             |
|                    +------------------------------------+                   |
|                    |             Welcome Back           |                   |
|                    | Enter your university credentials  |                   |
|                    |                                    |                   |
|                    | Student ID / Campus Email          |                   |
|                    | [ student@campus.edu             ] |                   |
|                    |                                    |                   |
|                    | Password                           |                   |
|                    | [ ******************          (o) ] |                   |
|                    |                                    |                   |
|                    | [ ] Remember me   Forgot Password? |                   |
|                    |                                    |                   |
|                    | +--------------------------------+ |                   |
|                    | |       Log In as Student        | |                   |
|                    | +--------------------------------+ |                   |
|                    |                                    |                   |
|                    | --------- Or switch role --------- |                   |
|                    | [  Log in as Administrator ->   ]  |                   |
|                    |                                    |                   |
|                    | Don't have an account? Sign Up     |                   |
|                    +------------------------------------+                   |
|                                                                             |
+-----------------------------------------------------------------------------+
```

---

### Screen 2: Student Dashboard
*Purpose: At-a-glance status overview, fast navigation, and upcoming reservation reminder.*

```
+---------------------+--------------------------------------------------------------+
| [Logo] CampusNest   | [Search resources...]              (3 Notifications) (Sarah) |
+---------------------+--------------------------------------------------------------+
| * Dashboard (Active)| Good morning, Sarah!                                         |
|   Explore Venues    | Student ID: STU-84920 - Computer Science                     |
|   My Bookings       |                                                              |
|   Profile           | +--------------------+ +------------------+ +--------------+ |
|   Logout            | | Active Bookings    | | Pending Approval | | Total Past   | |
|                     | |        1           | |        2         | |      8       | |
|                     | +--------------------+ +------------------+ +--------------+ |
|                     |                                                              |
|                     | NEXT UPCOMING RESERVATION                                    |
|                     | +----------------------------------------------------------+ |
|                     | | [Icon: Lab] CS Lab 304 - Machine Learning Session        | |
|                     | | Date: Tomorrow, Nov 19 | Time: 2:00 PM - 4:00 PM         | |
|                     | | Status: [APPROVED]    Location: Tech Block, 3rd Floor    | |
|                     | | [ View Booking Details ]            [ Cancel Booking ]   | |
|                     | +----------------------------------------------------------+ |
|                     |                                                              |
|                     | POPULAR CAMPUS RESOURCES              [ View All Venues -> ] |
|                     | +-------------------+  +------------------+  +-------------+ |
|                     | | Seminar Hall A    |  | Badminton Ct 2   |  | Physics Lab | |
|                     | | Cap: 150 | Blk B  |  | Cap: 4 | Gym     |  | Cap: 30     | |
|                     | | [ Check Slots ]   |  | [ Check Slots ]  |  | [Check Slots| |
|                     | +-------------------+  +------------------+  +-------------+ |
+---------------------+--------------------------------------------------------------+
```

---

### Screen 3: Explore Resources
*Purpose: Search, filter by category/capacity, and browse all campus venues.*

```
+---------------------+--------------------------------------------------------------+
| [Logo] CampusNest   | [Search resources...]              (Notifications) (Sarah v) |
+---------------------+--------------------------------------------------------------+
|   Dashboard         | EXPLORE CAMPUS FACILITIES                                    |
| * Explore (Active)  | Discover and book rooms, laboratories, halls & sports courts |
|   My Bookings       |                                                              |
|   Profile           | +----------------------------------------------------------+ |
|                     | | [Q Search by name or location...]         [Sort: Name v] | |
|                     | | Category: [All] [Hostel] [Labs] [Seminar Halls] [Sports] | |
|                     | | Capacity Filter: [Any Capacity v]  [Available Today Only]| |
|                     | +----------------------------------------------------------+ |
|                     |                                                              |
|                     | SHOWING 12 RESOURCES                                         |
|                     |                                                              |
|                     | +-------------------------+    +---------------------------+ |
|                     | | [ Image / Photo ]       |    | [ Image / Photo ]         | |
|                     | | Main Seminar Auditorium |    | Robotics & IoT Lab        | |
|                     | | Category: Seminar Hall  |    | Category: Laboratory      | |
|                     | | Location: Block A, Fl 1 |    | Location: Tech Park, Fl 2 | |
|                     | | Capacity: 250 People    |    | Capacity: 40 People       | |
|                     | | Amenities: AC, Mic, Proj|    | Amenities: Workstations   | |
|                     | | +---------------------+ |    | +-----------------------+ | |
|                     | | | View & Book Slots   | |    | | View & Book Slots     | | |
|                     | | +---------------------+ |    | +-----------------------+ | |
|                     | +-------------------------+    +---------------------------+ |
+---------------------+--------------------------------------------------------------+
```

---

### Screen 4: Resource Details & Time-Slot Booking
*Purpose: Inspect venue details, select date, pick available time slots, and submit booking request.*

```
+---------------------+--------------------------------------------------------------+
| [Logo] CampusNest   | <- Back to Explore Resources                                 |
+---------------------+--------------------------------------------------------------+
|   Dashboard         | Main Seminar Auditorium                                      |
| * Explore (Active)  | Block A, Ground Floor * Capacity: 250 * Category: Seminar Hall|
|   My Bookings       |                                                              |
|                     | +------------------------------+ +-------------------------+ |
|                     | | STEP 1: SELECT DATE          | | STEP 3: BOOKING DETAILS | |
|                     | | [<] November 2026 [>]        | |                         | |
|                     | | Su Mo Tu We Th Fr Sa         | | Purpose of Reservation: | |
|                     | |           1  2  3  4         | | [ Annual Hackathon    ] | |
|                     | |  5  6  7  8  9 10 11         | |                         | |
|                     | | 12 13 14 15 16 17 18         | | Expected Attendees:     | |
|                     | | 19[20]21 22 23 24 25         | | [ 120                 ] | |
|                     | +------------------------------+ |                         | |
|                     |                                  | Selected Slot:          | |
|                     | STEP 2: PICK TIME SLOT           | Nov 20, 10:00 - 12:00 PM| |
|                     | (Green = Free, Gray = Booked)    |                         | |
|                     | [ 08:00 - 10:00 AM ] [Booked]    | +---------------------+ | |
|                     | [*10:00 - 12:00 PM*] (Selected)  | | Submit Request (->) | | |
|                     | [ 12:00 - 02:00 PM ] [Available] | +---------------------+ | |
|                     | [ 02:00 - 04:00 PM ] [Booked]    | * Request will be sent  | |
|                     | [ 04:00 - 06:00 PM ] [Available] |   to admin for approval | |
|                     | +------------------------------+ +-------------------------+ |
+---------------------+--------------------------------------------------------------+
```

---

### Screen 5: My Bookings (Student History & Cancellation)
*Purpose: Full tracking of all user requests with real-time status badges and cancel trigger.*

```
+---------------------+--------------------------------------------------------------+
| [Logo] CampusNest   | [Search my bookings...]            (Notifications) (Sarah v) |
+---------------------+--------------------------------------------------------------+
|   Dashboard         | MY BOOKINGS & RESERVATIONS                                   |
|   Explore           | View and manage your current and previous campus bookings    |
| * My Bookings(Actv) |                                                              |
|   Profile           | Filter: [ All Bookings ] [ Upcoming ] [ Pending ] [ Past ]   |
|                     |                                                              |
|                     | +----------------------------------------------------------+ |
|                     | | Main Seminar Auditorium                                  | |
|                     | | Date: Nov 20, 2026 | Time: 10:00 AM - 12:00 PM           | |
|                     | | Purpose: Annual Hackathon Orientation                    | |
|                     | | Requested on: Nov 16, 2026                               | |
|                     | | Status: [ PENDING APPROVAL (Amber) ]                     | |
|                     | | Action: [ Cancel Booking Request (Red Outline) ]         | |
|                     | +----------------------------------------------------------+ |
|                     |                                                              |
|                     | +----------------------------------------------------------+ |
|                     | | Robotics & IoT Lab                                       | |
|                     | | Date: Nov 15, 2026 | Time: 02:00 PM - 04:00 PM           | |
|                     | | Purpose: IEEE Drone Workshop                             | |
|                     | | Status: [ APPROVED (Green) ]                             | |
|                     | | Action: [ Completed / Archived ]                         | |
|                     | +----------------------------------------------------------+ |
+---------------------+--------------------------------------------------------------+
```

---

### Screen 6: Admin Dashboard
*Purpose: High-level facility statistics, pending request volume, and quick admin shortcuts.*

```
+---------------------+--------------------------------------------------------------+
| [Logo] AdminNest    | [Search requests, users, rooms...]           (Admin: Prof. Roy)|
+---------------------+--------------------------------------------------------------+
| * Overview (Active) | ADMIN MANAGEMENT DASHBOARD                                   |
|   Booking Requests  | Campus Facilities & Approvals Center                         |
|   Resource Manager  |                                                              |
|   Audit Reports     | +------------------+ +------------------+ +----------------+ |
|   Settings          | | Pending Requests | | Approved Today   | | Total Venues   | |
|                     | |        7         | |        14        | |       24       | |
|                     | | [Action Needed]  | | +12% from ystd   | | 4 Categories   | |
|                     | +------------------+ +------------------+ +----------------+ |
|                     |                                                              |
|                     | URGENT PENDING APPROVAL QUEUE       [ View All Requests -> ] |
|                     | +----------------------------------------------------------+ |
|                     | | Sarah Doe - Seminar Hall A                               | |
|                     | | Date: Nov 20 (10:00 AM - 12:00 PM) * Purpose: Hackathon  | |
|                     | | Conflict Check: [No Overlap Detected (Green Check)]      | |
|                     | | [ (v) Approve ]        [ (x) Reject with Reason ]        | |
|                     | +----------------------------------------------------------+ |
|                     | | Kevin Miller - Basketball Court 1                        | |
|                     | | Date: Nov 21 (04:00 PM - 06:00 PM) * Purpose: Match      | |
|                     | | Conflict Check: [No Overlap Detected (Green Check)]      | |
|                     | | [ (v) Approve ]        [ (x) Reject with Reason ]        | |
|                     | +----------------------------------------------------------+ |
+---------------------+--------------------------------------------------------------+
```

---

### Screen 7: Admin Booking Management
*Purpose: Comprehensive management table with search, status filtering, and decision controls.*

```
+---------------------+--------------------------------------------------------------+
| [Logo] AdminNest    |                                              (Admin: Prof. Roy)|
+---------------------+--------------------------------------------------------------+
|   Overview          | BOOKING REQUESTS MANAGEMENT                                  |
| * Requests (Active) | Review, approve, or reject student reservation requests      |
|   Resource Manager  |                                                              |
|   Settings          | +----------------------------------------------------------+ |
|                     | | [Q Search student, venue, or purpose...]  Filter: [All v]| |
|                     | | Status Tabs: [All (21)] [*Pending (7)*] [Approved] [Rej] | |
|                     | +----------------------------------------------------------+ |
|                     |                                                              |
|                     | +----------------------------------------------------------+ |
|                     | | STUDENT    | RESOURCE     | DATE & TIME      | STATUS    | ACTIONS   | |
|                     | |------------+--------------+------------------+-----------+-----------| |
|                     | | Sarah Doe  | Seminar Hall | Nov 20, 10-12 PM | [Pending] | [Approve] | |
|                     | | ID: 84920  | Block A      | Purpose: Hackath |           | [Reject]  | |
|                     | |------------+--------------+------------------+-----------+-----------| |
|                     | | Alex Wong  | CS Lab 101   | Nov 20, 02-04 PM | [Pending] | [Approve] | |
|                     | | ID: 73391  | Tech Block   | Purpose: AI Exam |           | [Reject]  | |
|                     | |------------+--------------+------------------+-----------+-----------| |
|                     | | Maya Patel | Badminton C1 | Nov 18, 08-09 AM | [Approved]| [Details] | |
|                     | | ID: 91024  | Sports Ctr   | Purpose: Practice|           |           | |
|                     | +----------------------------------------------------------+ |
|                     | Showing 1 - 3 of 7 pending requests        [< Prev] [1] [Next >] |
+---------------------+--------------------------------------------------------------+
```

---

## 4. Reusable UI Components Inventory

| Component Name | Description & Usage |
|---|---|
| `SidebarNav` | Persistent navy blue sidebar with logo, role indicator, icons, and active state indicators. |
| `TopNavBar` | Breadcrumbs, universal search bar, notification bell with count badge, and user avatar dropdown. |
| `ResourceCard` | Display card for facilities with image thumbnail, category pill, capacity, location, and CTA button. |
| `StatusBadge` | Semantic colored pill (`Pending`, `Approved`, `Rejected`, `Cancelled`) with uniform typography. |
| `TimeSlotPicker` | Grid of selectable slot pills indicating real-time availability (`Available`, `Selected`, `Booked`). |
| `StatWidget` | Metric card used on dashboards displaying numerical KPIs, icon badges, and micro-labels. |
| `FilterBar` | Horizontal pill/chip selector for facility categories and quick-search input. |
| `ConfirmationModal` | Pop-up modal for destructive or final actions (e.g., student cancellation, admin rejection note). |

---

## 5. Responsive Behavior Matrix

- **Desktop (>= 1024px):**
  - Full expanded 256px (`w-64`) left sidebar.
  - Multi-column grids (3 to 4 cards per row for resources).
  - Side-by-side date picker and time-slot selector.
- **Tablet (768px – 1023px):**
  - Collapsible icon-only sidebar (64px `w-16`).
  - 2-column card grid for resource browsing.
  - Tables switch to horizontally scrollable wrappers.
- **Mobile (< 768px):**
  - Sidebar hidden behind a top hamburger drawer.
  - Single-column stacked cards (`grid-cols-1`).
  - Time-slot picker stacks vertically below the date picker.
  - Full-width action buttons for comfortable touch targets (minimum 44px height).
