# ABTalks - 60-Day Coding Challenge
## Master Prompt for Claude Code

> This file combines the project overview, detailed page specification, and implementation/continuation instructions generated from the existing ABTalks project documentation.
> Treat the requirements below as the source of truth for continuing the project. Do not invent requirements that are not specified here.

---

## 1. Project Overview

ABTalks is a complete learning platform designed for Indian students to build real-world projects through a 60-day coding challenge. The application guides users from onboarding through daily challenges, community interaction, and finally to earning a certificate of completion.

All data is stored locally in the browser using `localStorage`. No backend or database is required.

---

## 2. Core Requirements

- Complete user journey from landing page to certificate
- Streak tracking system with calendar visualization
- User profile management with avatar upload
- Coding track selection:
  - Full-Stack
  - DSA
  - AI/ML
  - Frontend
  - Backend
  - Mobile Dev
- Daily challenge submission with file upload
- Community feed with posts, replies, and live sessions
- Leaderboard with clickable user profiles
- Certificate generation upon completion

---

## 3. Complete User Flow

1. User lands on homepage
2. Goes through onboarding (Day 0)
3. Logs in (OTP or OAuth)
4. Selects coding track
5. Completes profile setup
6. Views dashboard
7. Accesses calendar for streak tracking
8. Completes daily challenges
9. Engages with community
10. Views leaderboard
11. Receives certificate of completion

---

## 4. Page Structure and Sequence

There are 11 pages including the landing page:

| # | File | Purpose |
|---|---|---|
| 1 | `index.html` | Landing page - entry point |
| 2 | `onboarding1.html` | Day 0 onboarding |
| 3 | `login1.html` | Authentication |
| 4 | `tracking1.html` | Coding track selection |
| 5 | `profile1.html` | User profile |
| 6 | `dashboard1.html` | Main dashboard |
| 7 | `calender1.html` | Streak tracking calendar |
| 8 | `day121.html` | Daily challenge |
| 9 | `community1.html` | Community feed |
| 10 | `leaderboard1.html` | Leaderboard |
| 11 | `certificate1.html` | Certificate/end of journey |

Navigation flow:

`index.html → onboarding1.html → login1.html → tracking1.html → profile1.html → dashboard1.html → calender1.html → day121.html → community1.html → leaderboard1.html → certificate1.html`

Certificate is the final page and must not have a Next button.

---

## 5. UI/UX Design System

### Color Palette

Dark theme with accent colors:

- Background: `#070D1F`, `#0A0E26`, `#050A1E`
- Primary Accent: `#FF6A1A`, `#FF8C42`, `#FF9A4A`, `#FFAB6A`
- Success: `#10B981`, `#6EE7B7`
- Error/Danger: `#EF4444`, `#FCA5A5`
- Gold: `#FFD700`, `#FCD34D`
- Purple: `#8B5CF6`, `#A78BFA`
- Text: `#FFFFFF`, `#8CA0C8`, `#7B8DB0`, `#5A6A8A`

### Typography

- Inter font family
- JetBrains Mono where appropriate

### Visual Style

- Mobile-first design specifically for 390px width
- Glass effects using backdrop blur and translucent backgrounds
- Gradient backgrounds on buttons and cards
- Rounded corners: approximately 12px–24px
- Box shadows for depth
- Emoji/unicode icons instead of external icon libraries

### Interaction Style

- Hover animations on interactive elements
- Transform, scale, and shadow effects
- Smooth transitions between 0.3s and 0.8s

---

## 6. Page-by-Page Requirements

### 6.1 Landing Page — `index.html`

- Animated code block with typewriter effect
- Live learner counter
- Animated statistics:
  - Students
  - Projects
  - Internship
- Multiple CTAs leading to onboarding
- Student testimonials

### 6.2 Onboarding — `onboarding1.html`

- Animated "0"
- Floating and pulse-ring effects
- Glowing orb animations in background
- Stats card:
  - 0 days
  - 0/30 challenges
  - 10 min
- Start Challenge button → `login1.html`
- Back button → `index.html`

### 6.3 Login — `login1.html`

- OAuth login with GitHub and Google, opening in a new tab
- OTP verification
- Six-digit OTP input
- Auto-advance on OTP input
- Copy/paste support for OTP
- Verify button → `tracking1.html`
- Back button → `onboarding1.html`

### 6.4 Track Selection — `tracking1.html`

- Six coding tracks with icons and descriptions
- Track persistence using `localStorage`
- Select/unselect functionality
- Selected track appears on profile page
- Continue → `profile1.html`
- Profile link → `profile1.html`
- Back → `login1.html`

### 6.5 Profile — `profile1.html`

- Avatar upload with preview
- PNG/JPG/PDF accepted according to existing specification
- Maximum file size: 10MB
- Edit profile modal containing:
  - Name
  - Bio
  - Location
  - Track
- Profile picture synced to dashboard
- Name synced to dashboard
- 60-day challenge progress bar
- Certificate section locked until 60 days are completed
- Notification toggle persisted with `localStorage`
- Back → `tracking1.html`
- Go to Dashboard → `dashboard1.html`

### 6.6 Dashboard — `dashboard1.html`

- Dynamic greeting using user name and avatar from `localStorage`
- Progress bar showing completion percentage
- Today's challenge card
- Statistic cards:
  - Streak
  - Challenges
  - XP
  - Doubts Solved
- Clickable stat cards with XP popup
- Days list showing:
  - Completed
  - Current
  - Locked
- Back → `profile1.html`
- Next → `calender1.html`

### 6.7 Calendar — `calender1.html`

- Real-time streak counter
- Enrollment date
- Working month navigation
- Interactive calendar with date statuses:
  - 🔥 Current streak days — green with fire icon
  - 💔 Broken days — red with broken-heart icon
  - ✅ Completed days — green
  - 🎯 Enrollment day — purple with target
  - ⭐ Past streaks of 3+ days — gold with star
- Past streak statistics
- Auto-refresh every 5 seconds
- Back → `dashboard1.html`
- Next → `day121.html`

### 6.8 Daily Challenge — `day121.html`

Three required tasks:

1. GitHub commit URL input with clear button
2. LinkedIn post URL input with clear button
3. Proof-of-work file upload

File upload:

- Drag and drop or tap
- Progress simulation

Functionality:

- Submit validation requires all three tasks
- Save as Draft
- Back → `calender1.html`
- Next → `community1.html`

### 6.9 Community — `community1.html`

- Filter chips:
  - All
  - Doubts
  - Showoff
  - Help
- Posts with image/file upload
- PNG/JPG/PDF support according to existing specification
- Maximum 10MB
- Reply section
- Auto-updating reply count
- Live mentor session
- Platform selection:
  - Zoom
  - Google Meet
  - Discord
- Upload area with drag/drop and progress bar
- Back → `day121.html`
- Next → `leaderboard1.html`

### 6.10 Leaderboard — `leaderboard1.html`

- Tabs:
  - Daily
  - Weekly
  - All Time
- XP scaling according to tab
- Podium:
  - 1st
  - 2nd
  - 3rd
- Top coder list with ranks
- Clicking a user opens a profile modal
- User statistics:
  - Rank
  - XP
  - Streak
- Back → `community1.html`
- Next → `certificate1.html`

### 6.11 Certificate — `certificate1.html`

- Certificate card with gold accents
- User name from `localStorage`
- Statistics:
  - Streak
  - XP
  - Challenges
- Download certificate as a text file
- LinkedIn share
- Twitter share
- Back → `leaderboard1.html`
- **No Next button**

---

## 7. Shared Components

Use consistent implementations across pages for:

- Toast notifications
  - Success/error messages
  - Slide up from bottom
- Fixed bottom navigation
  - Back
  - Next
- Circular avatar
  - Initials or uploaded image
- Animated toggle switch
- Animated progress bar
- Modal overlays
  - Blur backdrop
  - Centered modal box

### Navigation Pattern

- Top-left back arrow should use an anchor tag
- Bottom navigation contains Back/Next
- All navigation must use:
  `<a href="...">`
- Do not use `onclick`, `location.href`, or JavaScript navigation

---

## 8. Animations and Interactions

### CSS Animations

Maintain/use these established animations:

- `bgScroll` — scrolling dot pattern background
- `pulseGlow` — glowing orbs, 6s cycle
- `float` — floating numbers, 4s cycle
- `ringPulse` — expanding pulse rings, 4s cycle
- `pulse-green` — active streak glow
- `pulse-red` — broken streak glow
- `fadeIn`
- `fadeInUp`
- `slideDown`
- `slideUp`
- `popIn`

### Hover Effects

- Cards: `translateY(-4px)` with border-color change
- Buttons: `translateY(-2px) scale(1.02)` with enhanced shadow
- Navigation links: `translateY(-2px)` with shadow
- Tabs: `scale(1.02)`
- Day cells: `scale(1.08)`

### Interactive Behaviors

- Typewriter effect on landing page
- Live counter simulation
- OTP auto-advance
- File upload progress simulation
- Reply input auto-close behavior
- Real-time streak updates every 5 seconds
- Community filter chips
- Leaderboard tab switching

---

## 9. Responsive Design

The established design is intentionally fixed to 390px.

- Fixed width: `390px`
- Viewport:
  `width=390, initial-scale=1.0`
- Main `.phone` container:
  `width: 390px; min-height: 100vh`
- No media queries
- Mobile-first approach
- Include safe-area/bottom padding for fixed navigation

Do not convert the project into a responsive desktop layout unless explicitly instructed later.

---

## 10. Technology Requirements

### Frontend

- HTML5
- CSS3
  - Custom properties
  - Flexbox
  - Grid
  - Animations
- Vanilla JavaScript
- No frontend framework

### Fonts

- Google Fonts:
  - Inter
  - JetBrains Mono

### Storage

Use browser `localStorage` for persistence.

Known storage values include:

- `userName`
- `userAvatar`
- `userAvatarInitial`
- `codingTrack`
- `notifications`
- `trackSelected`
- `streak`
- `xp`
- `challenges`

---

## 11. Important Implementation Decisions

These decisions are part of the existing architecture:

1. Separate HTML pages are used.
2. Data is stored only in `localStorage`.
3. No backend or database.
4. Mobile-first design at 390px.
5. No React, jQuery, or other frameworks.
6. Emoji icons are used instead of icon libraries.
7. CSS is kept inside `<style>` tags in each HTML file.
8. JavaScript is kept inside `<script>` tags in each HTML file.
9. All pages use `.html`.
10. Page naming follows the `*1.html` convention.
11. Navigation uses `<a href>` tags.
12. Profile pictures are stored as base64 in `localStorage`.
13. Certificate is the final page.
14. Streak calculation counts consecutive "done" days and breaks on "broken" days.
15. Past streaks of 3+ days use gold and ⭐.
16. Calendar data generates realistic data for the past three months.

---

## 12. Things That Must NOT Be Changed

Unless explicitly instructed by the user:

- Do not change the `*1.html` file naming convention.
- Do not change the 390px fixed-width design.
- Do not add a backend or database.
- Do not change the established page sequence or flow.
- Do not rename the repository from `cipher_crew`.
- Do not add a Next button to `certificate1.html`.
- Do not remove existing navigation links.
- Do not change the dark theme palette.
- Do not use `onclick` or `location.href` for navigation.
- Do not add external dependencies or frameworks.
- Do not change the mobile-first approach.
- Do not add responsive media queries.
- Do not replace the existing architecture with React, Vue, etc.

---

## 13. Existing Project Status

According to the existing project documentation:

### Completed

- All 11 pages are complete and functional
- Full navigation flow is implemented
- `localStorage` persistence is working
- Animations and interactions are implemented
- Certificate page is complete

### Potential Enhancements — Not Required

- More challenge types in `day121.html`
- More community post examples
- More leaderboard users
- Enhanced certificate design with canvas/PDF generation
- Email/password login option
- Dark/light theme toggle

### Known Bugs

The existing documentation reports no known bugs:

- Navigation links work
- `localStorage` operations work
- Animations/interactions work
- Pages are functional

---

## 14. Claude Code Continuation Instructions

When continuing development:

1. Maintain the existing architecture.
2. Keep all persistence in `localStorage`.
3. Follow the existing page sequence.
4. Use anchor tags for navigation.
5. Keep the `*1.html` naming convention.
6. Keep the 390px mobile-first layout.
7. Preserve the dark theme and orange/gold accents.
8. Keep CSS and JavaScript self-contained in each HTML page.
9. Do not introduce external frameworks/libraries/icon packs.
10. Match the existing design patterns before creating new ones.
11. Use emojis for icons.
12. Test all navigation links after changes.
13. Do not add features that break the existing flow.

### Bug-Fixing Priority

1. Broken navigation links
2. `localStorage` issues
3. CSS/styling problems
4. JavaScript console errors

---

## 15. Testing Checklist

Before deployment or finalizing changes, verify:

- [ ] All 11 pages load without errors
- [ ] All navigation links work in sequence
- [ ] `localStorage` saves and retrieves data correctly
- [ ] Animations and transitions work smoothly
- [ ] Upload functionality works
- [ ] OTP input auto-advances correctly
- [ ] Calendar displays correctly for the current month
- [ ] Streak calculation is accurate
- [ ] Leaderboard displays users
- [ ] Certificate displays correct user data

---

## 16. Deployment

### Repository

- Repository: `cipher_crew`
- Project: **ABTalks**
- Existing live URL: `https://cipher-crew.netlify.app`

### Deployment

1. Push code to the `cipher_crew` GitHub repository.
2. Connect the repository to Netlify.
3. Deploy automatically on push.

---

## 17. Existing File/Folder Structure

Preserve the existing project structure where possible. The expected page files are:

```text
cipher_crew/
├── index.html
├── onboarding1.html
├── login1.html
├── tracking1.html
├── profile1.html
├── dashboard1.html
├── calender1.html
├── day121.html
├── community1.html
├── leaderboard1.html
└── certificate1.html
```

Add supporting assets only when required by the existing implementation, without introducing a framework-based architecture.

---

## 18. Final Instruction to Claude Code

You are continuing an existing ABTalks project, not starting a new project from scratch.

First inspect the existing files and understand the current implementation. Preserve working functionality and architecture.

When making changes:

- Follow this `prompt.md` as the project specification.
- Do not overwrite working features unnecessarily.
- Do not change architecture unless the user explicitly asks.
- Do not invent new requirements.
- Keep all existing page links functional.
- Keep the project deployable as a static Netlify website.
- Test the affected pages and navigation after making changes.
- If a requested change conflicts with these requirements, follow the user's explicit new instruction while changing only what is necessary.

The goal is to improve and continue the existing ABTalks website while preserving its established structure and behavior.
