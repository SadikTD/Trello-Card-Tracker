# TCTracker — Trello Card Tracker

A single-file web app that tracks cards created by a specific Trello board member. Connect with your API credentials, pick a target member, and instantly see every card they've added — with filters, sorting, history timelines, and CSV export.

## Features

- **Member-scoped scanning** — fetches only `createCard`, `copyCard`, and `moveCardToBoard` actions by your chosen member
- **Live board data** — pulls current list placement, labels, assigned members, and archive status for every card
- **Filters & search** — filter by list, label, status (active/archived), date range, or free-text title search
- **Sortable columns** — click any column header to sort ascending/descending
- **Card history timeline** — expand any row to see the full action history (moves, comments, label changes, etc.)
- **Bulk actions** — select cards, copy titles to clipboard, or export the filtered view as CSV
- **Auto-refresh** — optional polling interval (1 min – 30 min)
- **Dark / Light theme** — toggle with one click, preference saved locally
- **Keyboard shortcuts** — `Ctrl+F` to focus search, `R` to refresh
- **Zero dependencies** — pure HTML/CSS/JS in a single file, no build step

## Setup

### 1. Get Trello API Credentials

1. Go to [trello.com/power-ups/admin](https://trello.com/power-ups/admin) and create a new Power-Up (or use an existing one).
2. Copy your **API Key** from the Power-Up settings.
3. Generate a **Token** by visiting the authorization URL shown on the same page.

### 2. Find Your Board ID

Open your Trello board in the browser. The URL looks like:

```
https://trello.com/b/AbCdEfGh/my-board-name
                     ^^^^^^^^
                     This is your Board ID
```

### 3. Launch

Open `index.html` in any modern browser — no server required.

1. Enter your API Key, Token, and Board ID.
2. Click **Connect to Board**.
3. Select the target member and scan depth.
4. Click **Start Scanning**.

Credentials are saved to `localStorage` if "Remember credentials" is checked.

## Hosting on GitHub Pages

1. Push `index.html` to your repository's `main` branch.
2. Go to **Settings → Pages** and set the source to `main` / `/ (root)`.
3. Your tracker will be live at `https://<username>.github.io/<repo-name>/`.

> **Note:** Your API key and token are entered client-side and stored in your browser's `localStorage`. They are never sent anywhere except directly to the Trello API. However, if your repository is public, be aware that anyone can use the hosted page — they would still need their own credentials.

## Usage

| Action | How |
|--------|-----|
| Filter cards | Use the dropdowns and search bar above the table |
| Sort | Click any column header |
| View card history | Click **▶ History** on any row |
| Copy titles | Select rows with checkboxes, then **Copy Selected** |
| Export | Click **Export CSV** to download the current filtered view |
| Change target member | Open **Settings** and pick a different member |
| Adjust scan depth | Settings → Scan Depth (higher = slower but more complete) |

## Tech Stack

- Vanilla HTML, CSS, and JavaScript
- [Trello REST API](https://developer.atlassian.com/cloud/trello/rest/)
- Fonts: JetBrains Mono + Outfit (loaded from Google Fonts)

## License

MIT
