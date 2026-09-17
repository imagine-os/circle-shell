# Circle app shell rebuild

A high-fidelity, static front-end recreation of the [Circle](https://circle.so) community platform's logged-in app shell, built as a single self-contained `index.html` (inline CSS and JS, no build step, no backend).

Everything on the page is **mock data**: the community "Maker Circle", its spaces, members, posts, events, courses, notifications and messages are invented. Interactions (likes, polls, RSVPs, follows, the composer, DMs, the command palette, dark mode) work locally in the browser and reset on reload, except for the theme and collapsed sidebar groups, which are remembered in `localStorage`.

**Live site:** <https://imagine-os.github.io/circle-shell/> — the site deploys from `main` via the Pages workflow (`.github/workflows/pages.yml`) to the `gh-pages` branch.

## Open it

- Double-click `index.html`, or
- serve the folder: `python3 -m http.server 8000` and open <http://localhost:8000/>.

Keyboard: `⌘K` / `Ctrl+K` opens search, `Esc` closes any overlay.

## What is in the shell

- Left sidebar with community switcher, pinned links (Home, Members, Events, Courses, Leaderboard) and collapsible space groups.
- Top bar with search, theme toggle, notifications, direct messages, "New post" and account menu.
- Feed with space header, tabs, composer, sort/filter row and post cards (text, image, poll, event, pinned announcement, course progress, comment threads).
- Right rail: about, upcoming events, top members, trending.
- Members, Events, Courses and Leaderboard views; notifications drawer; DM popover; command palette.
- A "Live now" indicator in the top bar that opens the live room.
- Light and dark themes via CSS variables; responsive down to phone width.

## Space types

Every space in the sidebar carries a small type icon, and the space header shows the matching type label, mirroring Circle's space types:

| Type | Space in the demo | What the view does |
| --- | --- | --- |
| Posts | Welcome, Introductions, Announcements, General, Show & Tell, Ask for Help, Wins | Feed with composer, sort and filter row, post cards (text, image, poll, event, course progress, pinned), comments. |
| Chat | Water Cooler | Channel-style chat grouped by day, hover actions (react, reply in thread, more), thread side panel, typing indicator, pinned message bar, members-online count, composer. |
| Events | Weekly Office Hours, Live Q&A (and the global Events page) | Upcoming list, month calendar toggle with event chips and a click-to-detail panel, event detail with RSVP, Add to calendar, attendee stack and "Join live" for a live event. |
| Course | Design Fundamentals, Launch Playbook | Course cards open the lesson player: curriculum sidebar with sections, completed ticks, current and locked lessons; video placeholder, lesson body, "Mark complete" that advances progress, prev/next, discussion. |
| Members | Members tab on every space, plus the global Members page | Searchable, filterable member grid with follow and message. |
| Images | Gallery | Masonry gallery with author chips and like counts, lightbox with prev/next, like and comments, Upload button. |
| Live room | Community Lounge | Pre-join card (camera preview, mic/camera toggles, display name), then a video-call stage: participant grid with a rotating "speaking" ring, muted badges and a screen-share tile; control bar (mic, camera, share, raise hand, reactions with emoji burst, participants, chat, leave); side panel with Chat, Participants (host/co-host badges, mute all) and Q&A; LIVE badge, running timer and recording indicator. |
| Live stream | Launch Day Stream | 16:9 player with LIVE pulse, ticking viewer count and animated waveform, a "Going live in" scheduled state with countdown and "Notify me", host row, auto-scrolling stream chat and a Replays list. |

## Deploy

Pushing to `main` runs `.github/workflows/pages.yml`, which publishes the site to an orphan `gh-pages` branch with plain git. Point GitHub Pages at the `gh-pages` branch (root) once.
