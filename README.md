# PulseDesk — Call Centre Operations

[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue.svg)](https://www.typescriptlang.org/)
[![React](https://img.shields.io/badge/React-19.x-61dafb.svg)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-8.x-646cff.svg)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v4-38bdf8.svg)](https://tailwindcss.com/)
[![Recharts](https://img.shields.io/badge/Recharts-3.x-22c55e.svg)](https://recharts.org/)

**PulseDesk** is a production-quality, responsive web application designed for call centre operations supervisors to monitor representatives, track daily performance, review call activity, manage multi-shift schedules, and proactively identify agents requiring support.

---

## 1. Project Objective

The objective of **PulseDesk** is to provide call centre operations teams with a single pane of glass for real-time telemetry, agent availability, SLA compliance monitoring, and workforce scheduling. Built desktop-first with full tablet and mobile responsiveness, PulseDesk delivers a clean SaaS aesthetic, consistent status tokens, and seamless LocalStorage persistence without requiring external servers or paid dependencies.

---

## 2. Key Features and User Workflows

### 📊 1. Overview Dashboard (`/`)
- **6 Core Operational KPI Cards**:
  - **Total Agents**: Full workforce count with month-over-month growth.
  - **Agents Online**: Live floor presence count and utilization percentage.
  - **Calls Handled Today**: Handled call count with volume comparison vs yesterday.
  - **Average Handling Time (AHT)**: Time per interaction with target threshold indicator.
  - **Customer Satisfaction (CSAT)**: Composite score benchmarked against target quality goals.
  - **Service Level (SLA)**: % of calls answered within SLA threshold (<20 seconds).
- **Interactive Visualizations (Recharts)**:
  - **7-Day Call Volume Trend**: Area chart comparing Inbound vs Outbound volumes.
  - **Call Outcome Distribution**: Donut chart detailing Resolved, Escalated, Follow-up, and Dropped calls.
  - **Agent Performance Comparison**: Bar chart benchmarking top performers by volume and CSAT.
- **Floor Availability Grid**: Real-time agent status tracker with instant status change selector (`Available`, `Busy`, `Break`, `Offline`).
- **Recent Call Activity**: Live log table with quick call inspection modal.
- **Supervisor Operational Alerts Banner**: Realistic notifications with one-click deep links to relevant agent or call records.

### 👥 2. Agents Management (`/agents`)
- **Searchable, Sortable, Paginated Table & Grid**:
  - Full-text search across Agent Name, ID (`AGT-xxx`), Email, and specialized skills.
  - Filter by Team (`Inbound Support`, `Technical Care`, `Escalations`, `Billing & Retention`) and Status.
  - Multi-column sorting (Name, Calls Handled, AHT, CSAT, Missed Calls).
  - Configurable pagination (5, 10, or 20 per page).
  - Table vs Grid Cards view toggle.
- **Complete CRUD Operations (LocalStorage Persisted)**:
  - **Add Agent**: Form modal with validation for Name, Email, Extension Phone, Team, Role, Status, and Skills.
  - **Edit Agent**: Modify representative details and role assignments.
  - **Inline Status Changer**: Modify agent presence on the fly from table rows.
  - **Delete Agent**: Destructive action protected by a confirmation dialog.
  - **Agent Detail Modal**: Comprehensive profile displaying contact info, performance tiles, routing skill tags, scheduled shifts, and recent interactions.

### 📞 3. Call Activity & Logs (`/calls`)
- **Telephony Interaction Log**:
  - Search by Call ID (`CAL-xxx`), Customer Name, Phone, or Representative.
  - Filter by Outcome (`Resolved`, `Escalated`, `Follow-up`, `Dropped`), Call Type (`Inbound`, `Outbound`, `Escalated`), Category, and Date (`Today`, `Yesterday`, `Past 7 Days`).
  - Sortable by Timestamp, Duration, Customer, or Agent.
  - Duration and timestamp formatting with SLA compliance badges.
- **Interactive Call Detail Modal**:
  - Customer contact details, queue wait time, sentiment gauge (`Positive`, `Neutral`, `Negative`).
  - **Audio Recording Simulator**: Interactive audio player mockup with scrubber and duration progress.
  - **Supervisor & Agent Notes Editor**: Edit and persist call resolution remarks directly to local state.
- **Export CSV Button**: Prominent download button generating formatted CSV file of all currently filtered interactions.

### 📅 4. Staff Schedules & Rosters (`/schedules`)
- **Dual Schedule Views**:
  - **Weekly Calendar Grid View**: Day-by-day columns for the active week with shift cards and add shortcuts.
  - **Daily Timeline View**: Chronological roster listing for focused shift supervision.
- **Shift Allocations & Validation**:
  - Color-coded shift badges: Morning (Sky), Evening (Amber), Night (Indigo).
  - Start/End time tracking and break allowances (`30m`, `45m`, `60m`).
  - **Overlap & Collision Detection**: Warns the supervisor if an agent has overlapping shift assignments on the same date.
  - Add, edit, and delete shift assignments with instant LocalStorage sync.

### 📈 5. Operational Analytics & QA Reports (`/reports`)
- **Date Range Toggling**: Switch between `Today`, `Last 7 Days`, and `Last 30 Days`.
- **Summary Metrics**: Total Volume, First Contact Resolution (FCR), Global SLA Compliance, and Peak Traffic Hour.
- **Analytical Charts**:
  - Call Throughput vs Resolution Velocity (Bar Chart).
  - Outcome Breakdown (Pie Chart).
  - Average Handling Time trend against 240s benchmark (Line Chart).
  - CSAT satisfaction trend against target goal (Line Chart).
- **Representative Leaderboard**: Complete performance table ranked by CSAT and throughput.
- **Export Report CSV**: One-click download of the complete operational quality report.

### ⚙️ 6. Workspace & Supervisor Settings (`/settings`)
- **Supervisor Profile**: Name, Role, Email, and Call Centre Workspace name.
- **SLA & Quality Targets**: Configurable SLA %, Target CSAT %, and Target AHT in seconds.
- **Notification Preferences**: Toggles for High Missed Call Alerts, SLA Breach Warnings, and Shift Overlap Alerts.
- **Local Data Management**:
  - **Backup JSON**: Download full export of current workspace state (Agents, Calls, Shifts, Settings).
  - **Reset to Factory Demo**: Reset all state back to initial deterministic demonstration data with confirmation dialog.

---

## 3. Technology Stack

- **Framework**: [React 19](https://react.dev/) with [TypeScript](https://www.typescriptlang.org/)
- **Bundler & Build Tool**: [Vite 8](https://vitejs.dev/)
- **Styling**: [Tailwind CSS v4](https://tailwindcss.com/) with custom tokens
- **Routing**: [React Router v7](https://reactrouter.com/)
- **Icons**: [Lucide React](https://lucide.dev/)
- **Data Visualizations**: [Recharts v3](https://recharts.org/)
- **State Management & Persistence**: React Context API (`AppContext`) + `localStorage`
- **Data Export**: Native browser Blob CSV generation with character escaping

---

## 4. Prerequisites

To run this application locally, ensure you have:
- **Node.js**: v18.0.0 or higher (v20+ or v22+ recommended)
- **npm**: v9.0.0 or higher

Check your installed versions:
```bash
node -v
npm -v
```

---

## 5. Installation and Run Instructions

### 1. Clone or navigate to the repository:
```bash
cd /path/to/On-Ground.ai
```

### 2. Install dependencies:
```bash
npm install
```

### 3. Run the development server:
```bash
npm run dev
```
Open your browser and navigate to the printed local URL (typically `http://localhost:5173/`).

### 4. Build for production:
```bash
npm run build
```

### 5. Preview production build locally:
```bash
npm run preview
```
Open `http://localhost:4173/` in your browser.

---

## 6. Project Directory Structure

```
On-Ground.ai/
├── public/                 # Static assets
├── src/
│   ├── components/
│   │   ├── agents/         # Agent modals (Add, Edit, Detail inspection)
│   │   │   ├── AgentDetailModal.tsx
│   │   │   └── AgentModal.tsx
│   │   ├── calls/          # Call detail modal with audio simulator
│   │   │   └── CallDetailModal.tsx
│   │   ├── dashboard/      # Overview KPI cards and Recharts components
│   │   │   ├── AgentLiveStatusList.tsx
│   │   │   ├── AgentPerformanceChart.tsx
│   │   │   ├── CallsTrendChart.tsx
│   │   │   ├── KpiCard.tsx
│   │   │   ├── OutcomePieChart.tsx
│   │   │   └── RecentCallsTable.tsx
│   │   ├── layout/         # Shared persistent application shell
│   │   │   ├── AppLayout.tsx
│   │   │   ├── Sidebar.tsx
│   │   │   └── TopNavbar.tsx
│   │   ├── schedules/      # Shift assignment and validation modals
│   │   │   └── ShiftModal.tsx
│   │   └── ui/             # Accessible reusable UI primitives
│   │       ├── ConfirmDialog.tsx
│   │       ├── EmptyState.tsx
│   │       ├── Modal.tsx
│   │       └── ToastContainer.tsx
│   ├── context/
│   │   └── AppContext.tsx  # Centralized state management & LocalStorage sync
│   ├── data/               # Deterministic demonstration datasets
│   │   ├── initialSettings.ts
│   │   ├── mockAgents.ts   # 16 realistic agents across 4 teams
│   │   ├── mockAlerts.ts   # Clickable supervisor operational alerts
│   │   ├── mockCalls.ts    # 50+ realistic call detail records
│   │   └── mockSchedules.ts# 20+ shift assignments across shifts & teams
│   ├── pages/              # 6 Core Application views
│   │   ├── Agents.tsx
│   │   ├── CallActivity.tsx
│   │   ├── Overview.tsx
│   │   ├── Reports.tsx
│   │   ├── Schedules.tsx
│   │   └── Settings.tsx
│   ├── types/
│   │   └── index.ts        # TypeScript interfaces (Agent, CallRecord, Shift, etc.)
│   ├── utils/
│   │   └── index.ts        # CSV export, date/duration formatters, badge styles
│   ├── App.tsx             # Root router configuration
│   ├── index.css           # Tailwind CSS imports & global typography tokens
│   ├── main.tsx            # DOM mount entry point
│   └── vite-env.d.ts       # Vite client types declaration
├── index.html              # HTML5 entry with Inter font & meta tags
├── package.json            # Project dependencies and npm scripts
├── tsconfig.json           # TypeScript configuration with bundler resolution
├── vite.config.ts          # Vite configuration with React & Tailwind plugins
└── README.md               # Project documentation
```

---

## 7. Mock Data & LocalStorage Architecture

The application uses deterministic sample data initialized on first boot:
- **16 Agents** (`INITIAL_AGENTS`) distributed across 4 teams (`Inbound Support`, `Technical Care`, `Escalations`, `Billing & Retention`).
- **50+ Call Records** (`INITIAL_CALLS`) spanning various dates, categories, durations, and outcomes.
- **20+ Shift Assignments** (`INITIAL_SHIFTS`) covering Morning, Evening, and Night shifts.
- **Operational Alerts** (`INITIAL_ALERTS`) with actionable deep links.

### LocalStorage Persistence Keys:
- `pulsedesk_v1_agents`
- `pulsedesk_v1_calls`
- `pulsedesk_v1_shifts`
- `pulsedesk_v1_alerts`
- `pulsedesk_v1_settings`

Any changes made in the UI (creating an agent, modifying a shift, updating call notes, changing an agent's status, or editing settings) are automatically saved to `localStorage`. You can refresh the browser or close the tab, and your changes will remain intact.

To return to the initial baseline at any time, click **"Reset to Factory Demo Data"** from either the Supervisor profile menu in the top bar or the **Settings** page.

---

## 8. Limitations & Scope

- **No Live Backend / Database**: This frontend demonstration runs entirely client-side using local mock state and browser storage.
- **No Real-Time Telephony Carrier Integration**: Real SIP/VoIP trunk telephony, WebRTC softphones, and carrier recording streams are simulated using deterministic sample logs and an interactive audio player mockup.
- **Demonstration Data**: All agent names, customer names, telephone numbers, and notes are realistic mock samples created solely for testing. No real personal information is used.

---

## 9. AI Tools Used

In compliance with assignment requirements, the following AI tools were utilized during development:
- **Antigravity (Google DeepMind)**: Advanced agentic coding assistant used for architectural design, code generation, component modularization, TypeScript type safety validation, and documentation generation.

---

## 10. Verification & Feature Testing Guide

To verify all required features and workflows:

1. **Verify Navigation**:
   - Click through all sidebar links: **Overview**, **Agents**, **Call Activity**, **Schedules**, **Reports**, and **Settings**.
   - Notice the active route visual highlight in the sidebar and matching breadcrumbs in the top bar.
2. **Verify Global Search**:
   - Type `Marcus` or `CAL-901` in the top bar search input.
   - Click a search result to immediately navigate to the matching record.
3. **Verify Overview Dashboard**:
   - Check the 6 KPI cards displaying live values and trend comparisons.
   - Hover over the 3 Recharts visualizations (Area, Donut, and Bar charts) to inspect rich tooltips.
   - In the "Live Agent Availability" panel, change an agent's status dropdown (e.g., from `Available` to `On Break`) and observe the instantaneous count update.
   - Click the "Investigate" button on the amber alert banner to jump directly to the flagged agent.
4. **Verify Agents CRUD & Filtering**:
   - On the **Agents** page, search for `Priya`.
   - Toggle between **Table View** and **Grid View**.
   - Click **"Add Representative"**, fill out the form, and submit. Verify the new representative is added and persisted.
   - Click the eye icon on an agent row to view their full operational profile modal.
   - Click the trash icon to test the delete confirmation modal.
5. **Verify Call Activity & CSV Export**:
   - On the **Call Activity** page, filter by Outcome = `Dropped`.
   - Click any call row to open the Call Record modal. Test the audio recording playback simulation and edit the supervisor notes.
   - Click **"Export CSV"** and verify that a `.csv` file downloads with all matching call records.
6. **Verify Scheduling & Conflict Detection**:
   - On the **Schedules** page, toggle between **Weekly Grid** and **Daily Timeline**.
   - Click **"Assign Shift"**. Attempt to create a shift with an end time earlier than the start time to verify time validation.
   - Attempt to assign an overlapping shift to an agent already scheduled on that date to verify conflict warning detection.
7. **Verify Reports & Analytics**:
   - On the **Reports** page, click the date range toggles (`Today`, `Last 7 Days`, `Last 30 Days`) and observe the chart and volume metric updates.
   - Click **"Export Report CSV"** to download the formatted performance report.
8. **Verify Settings & Reset**:
   - On the **Settings** page, modify the Supervisor Name or SLA target, click **"Save Changes"**, and verify the notification toast appears.
   - Click **"Backup JSON"** to download a full JSON state snapshot.
   - Click **"Reset to Factory Demo"** to restore all data to its original state.

---

## 11. Screenshots Section

| Dashboard Overview | Agents Management Table |
|:---:|:---:|
| *(Overview dashboard with KPI cards, 7-day trend, outcome breakdown, and live floor availability)* | *(Agent roster with search, team filters, status pill selectors, and action controls)* |

| Call Activity & Audio Simulator | Weekly Staff Scheduling Grid |
|:---:|:---:|
| *(Call detail records with outcome badges, recording player mockup, and supervisor notes)* | *(Weekly calendar view with Morning, Evening, and Night shift assignments)* |

---

*PulseDesk — Call Centre Operations Management System | On-Ground.ai Assignment*
