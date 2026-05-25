# Smart Tech IT & Marketing Solution - OpenClaw Agent Dashboard

## Concept & Vision

A sophisticated AI automation command center that feels like piloting a spacecraft — precise, powerful, and professional. The dashboard embodies the cutting-edge nature of AI automation services while remaining approachable for business operations. It's where complex AI workflows become tangible business outcomes.

**Business Context:** Smart Tech IT & Marketing Solution provides AI automation services to help businesses streamline operations, automate repetitive tasks, and implement intelligent workflows.

## Design Language

### Aesthetic Direction
Dark mode command center with glowing cyan accents — inspired by sci-fi control rooms and premium SaaS dashboards. Think Bloomberg Terminal meets modern AI interfaces.

### Color Palette
- **Primary Background:** #0a0f1a (deep space)
- **Secondary Background:** #111827 (card surfaces)
- **Tertiary Background:** #1f2937 (elevated elements)
- **Primary Accent:** #06b6d4 (cyan glow)
- **Secondary Accent:** #8b5cf6 (purple highlight)
- **Success:** #10b981 (emerald)
- **Warning:** #f59e0b (amber)
- **Error:** #ef4444 (red)
- **Text Primary:** #f9fafb
- **Text Secondary:** #9ca3af
- **Text Muted:** #6b7280

### Typography
- **Headings:** Inter (700, 600) — clean, modern, highly legible
- **Body:** Inter (400, 500) — consistent family
- **Monospace:** JetBrains Mono — for metrics, code, IDs

### Spatial System
- Base unit: 4px
- Component padding: 16px, 24px
- Section gaps: 24px, 32px
- Border radius: 8px (cards), 6px (buttons), 4px (inputs)

### Motion Philosophy
- Micro-interactions: 150ms ease-out
- Page transitions: 300ms ease-in-out
- Data loading: skeleton shimmer
- Hover states: subtle glow intensification
- Success feedback: pulse animation

### Visual Assets
- Icons: Lucide React (consistent stroke width)
- Charts: Recharts with custom styling
- Decorative: Subtle grid patterns, glowing borders

## Layout & Structure

### Overall Architecture
```
┌─────────────────────────────────────────────────────────┐
│  Top Bar (Logo, Search, Notifications, Profile)         │
├──────────┬──────────────────────────────────────────────┤
│          │                                              │
│  Sidebar │           Main Content Area                  │
│  (Nav)   │                                              │
│          │                                              │
└──────────┴──────────────────────────────────────────────┘
```

### Page Structure
1. **Auth Pages** — Full-screen centered cards with animated background
2. **Dashboard** — Grid of metric cards + charts + recent activity
3. **Agents** — Card grid with agent status, quick actions
4. **Workflows** — Visual workflow builder preview + list
5. **Clients** — Table with search, filter, client cards
6. **Analytics** — Full-width charts with date range selector
7. **Settings** — Sectioned form layout

### Responsive Strategy
- Desktop: Full sidebar (240px) + expanded content
- Tablet: Collapsed sidebar (icons only) + full content
- Mobile: Bottom navigation + stacked content

## Features & Interactions

### Authentication
- **Login:** Email + password with "Remember me"
- **Register:** Business name, email, password, confirm password
- **Forgot Password:** Email input → success message
- **Logout:** Confirmation → redirect to login
- Session persistence via localStorage

### Dashboard Overview
- **Metric Cards:** Total Agents, Active Workflows, Clients Served, Revenue MRR
- **Quick Actions:** Create Agent, New Workflow, Add Client
- **Activity Feed:** Real-time recent actions
- **Performance Chart:** 30-day workflow executions

### Agent Management
- **Agent Cards:** Name, status indicator, specialty, last active
- **Status Types:** Active (green), Idle (yellow), Offline (gray)
- **Actions:** Start, Stop, Configure, View Logs, Delete
- **Create Agent:** Modal with name, type, configuration

### Workflow Automation
- **Workflow Cards:** Name, trigger type, status, execution count
- **Visual Builder Preview:** Node-based preview (simplified)
- **Templates:** Pre-built workflow templates
- **Execution History:** Log of recent runs with status

### Client Management
- **Client Table:** Name, email, plan, agents assigned, status
- **Search:** Real-time filtering
- **Actions:** View, Edit, Upgrade/Downgrade, Archive
- **Add Client:** Slide-out panel form

### Analytics
- **Date Range Selector:** Last 7/30/90 days, custom range
- **Charts:** Workflow success rate, agent utilization, revenue trends
- **Export:** CSV download option

### Settings
- **Profile:** Business info, avatar, contact details
- **Team:** Invite team members (mock)
- **Integrations:** Connected services display
- **Billing:** Plan details, usage metrics

## Component Inventory

### Navigation
- **Sidebar Item:** Icon + label, active state (cyan glow + bg), hover (subtle bg)
- **Mobile Nav:** Fixed bottom bar with 5 main items

### Cards
- **Metric Card:** Icon, value (large), label, trend indicator
- **Agent Card:** Avatar placeholder, name, status dot, actions dropdown
- **Workflow Card:** Title, trigger badge, status, run count, last run

### Forms
- **Input:** Dark bg, subtle border, focus (cyan border glow), error state
- **Button Primary:** Cyan bg, white text, hover (lighter), disabled (muted)
- **Button Secondary:** Transparent, cyan border, hover (filled)
- **Toggle:** Sliding switch with smooth animation

### Data Display
- **Table:** Striped rows, sticky header, hover highlight
- **Badge:** Pill-shaped status indicators
- **Avatar:** Circular placeholder with initials

### Feedback
- **Toast:** Slide-in notifications, auto-dismiss, action button
- **Modal:** Centered, backdrop blur, close button
- **Skeleton:** Shimmer animation for loading states

## Technical Approach

### Framework & Architecture
- **Framework:** React 18 with Vite
- **Routing:** React Router v6
- **State:** React Context + useReducer for auth, local state for UI
- **Styling:** Tailwind CSS with custom configuration
- **Charts:** Recharts
- **Icons:** Lucide React

### Data Persistence
- **Auth State:** localStorage with JWT-like token simulation
- **Database:** localStorage with JSON structure
  - users[]
  - agents[]
  - workflows[]
  - clients[]
  - activities[]

### API Simulation
- Mock async functions with setTimeout delays
- Simulated network responses for all CRUD operations
- Error simulation capability

### File Structure
```
src/
├── components/
│   ├── layout/
│   │   ├── Sidebar.tsx
│   │   ├── TopBar.tsx
│   │   └── MobileNav.tsx
│   ├── cards/
│   │   ├── MetricCard.tsx
│   │   ├── AgentCard.tsx
│   │   └── WorkflowCard.tsx
│   ├── forms/
│   │   ├── Input.tsx
│   │   ├── Button.tsx
│   │   └── Select.tsx
│   └── ui/
│       ├── Modal.tsx
│       ├── Toast.tsx
│       ├── Badge.tsx
│       └── Table.tsx
├── pages/
│   ├── auth/
│   │   ├── Login.tsx
│   │   └── Register.tsx
│   ├── Dashboard.tsx
│   ├── Agents.tsx
│   ├── Workflows.tsx
│   ├── Clients.tsx
│   ├── Analytics.tsx
│   └── Settings.tsx
├── context/
│   └── AuthContext.tsx
├── data/
│   └── mockData.ts
├── hooks/
│   └── useToast.ts
├── types/
│   └── index.ts
├── utils/
│   └── helpers.ts
├── App.tsx
└── main.tsx
```
