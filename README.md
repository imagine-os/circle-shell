# Circle app shell rebuild

A high-fidelity, static front-end recreation of the [Circle](https://circle.so) community platform's logged-in app shell, built as a single self-contained `index.html` (inline CSS and JS, no build step, no backend).

Everything on the page is **mock data**: the community "Maker Circle", its spaces, members, posts, events, courses, notifications and messages are invented. Interactions (likes, polls, RSVPs, follows, the composer, DMs, the command palette, dark mode) work locally in the browser and reset on reload, except for the theme and collapsed sidebar groups, which are remembered in `localStorage`.

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
- Light and dark themes via CSS variables; responsive down to phone width.

## Deploy

Pushing to `main` runs `.github/workflows/pages.yml`, which publishes the site to an orphan `gh-pages` branch with plain git. Point GitHub Pages at the `gh-pages` branch (root) once.
