# Hero Realms Health Counter

**[https://slopdotjpg.github.io/hero_realms_counter/](https://slopdotjpg.github.io/hero_realms_counter/)**

A single-file static web app for tracking player health during [Hero Realms](https://www.herorealms.com/) games. No server, no dependencies, no install — just open `index.html` in a browser.

## Features

- **2–6 players** with individual names and starting health
- **Class selection** per player with auto-filled starting HP
- **Pending system** — accumulate damage/healing before committing
- **Undo** — revert the last validated change per player
- **Keyboard shortcuts** for fast play
- **Change history** log per player card
- Health is capped at starting maximum (no over-healing)

## Classes

| Class   | Starting HP |
|---------|-------------|
| Cleric  | 55          |
| Fighter | 60          |
| Ranger  | 58          |
| Thief   | 52          |
| Wizard  | 50          |

## Usage

### Setup screen

1. Pick the number of players (2–6).
2. Optionally set a **default starting health** (used when no class is selected).
3. For each player, enter a name and select a class — or type a custom HP value directly.
4. Click **Begin the Battle**.

### Game screen

Each player card has:

- **−5 / − / + / +5** buttons that add to a **pending** delta (nothing is applied yet).
- A **custom amount** field with **−** and **+** buttons for larger adjustments.
- A **Pending** preview showing the accumulated delta and projected HP once pending is non-zero.
- **✓ Validate** — commits the pending change to the player's HP.
- **✗ Cancel** — discards the pending change without altering HP.
- **↩ Undo** — appears after each validation; reverts the last committed change.

### Keyboard shortcuts

| Key | Action |
|-----|--------|
| `Tab` / `Shift+Tab` | Cycle focus forward / backward through players |
| `↑` / `↓` | Add +1 / −1 to the focused player's pending |
| `Shift+↑` / `Shift+↓` | Add +5 / −5 to the focused player's pending |
| `Enter` | Validate the focused player's pending |
| `Esc` | Cancel the focused player's pending |

Click any card to focus it. The focused card is highlighted with a gold border and scrolls into view automatically.

## Layout

| Players | Layout |
|---------|--------|
| 2       | 2 columns |
| 3       | 3 columns |
| 4       | 4 columns (compact) |
| 5       | 3 + 2   |
| 6       | 3 + 3   |

## Running

```
open index.html
```

Or drag `index.html` into any modern browser. Works fully offline — no external requests.

## Mobile

The layout is fully responsive and touch-friendly. On small screens the grid adapts to 2–3 columns, buttons are sized for tap targets, and the keyboard shortcut hint is hidden. Orientation changes are handled automatically.

## Fonts

[Cinzel](https://fonts.google.com/specimen/Cinzel) is bundled in `fonts/` under the [SIL Open Font License 1.1](fonts/OFL.txt).
