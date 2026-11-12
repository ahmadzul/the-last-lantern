# Requirements: The Last Lantern

## Goal
Deliver a short, polished haunted-house escape game that a first-time player can understand and finish in one sitting, without an account or network access.

## User stories

### Start and understand the game
**As a player,** I want a short introduction and a clear objective before the timer starts, **so that** I know what I am trying to do.

Acceptance criteria:
- The initial screen explains that the player should find the back door and leave before the candle timer expires.
- The countdown begins only after the player chooses to enter or continue.
- The player can restart from the top of the page or the ending screen.

### Explore rooms
**As a player,** I want to move among the foyer, study, cellar, and back door, **so that** I can investigate the house in a useful order.

Acceptance criteria:
- The current room is visibly indicated in the room map.
- The back door remains unavailable until the iron key is found.
- Each room has a short, readable description and actions appropriate to its state.

### Solve the escape sequence
**As a player,** I want environmental clues to lead me through a small puzzle chain, **so that** solving the escape feels earned rather than random.

Acceptance criteria:
- The foyer contains a matchbook, a brass key, and a burned clipping that reveals the year 1893.
- The brass key lets the player attempt the study drawer; entering 1893 opens it and yields a candle.
- In the cellar, the player can light the candle using the matchbook; the light reveals the iron key.
- The iron key unlocks the back door and leads to a clear winning ending.
- A wrong year gives helpful feedback without losing progress.

### Track clues and objects
**As a player,** I want collected objects and discovered clues to remain visible, **so that** I can remember what I have learned.

Acceptance criteria:
- Collected objects appear in an inventory panel.
- Important discoveries appear in a field-notes panel.
- Progress survives a browser refresh on the same device; the player can restart to clear it.

### Accessibility and comfort
**As a player,** I want the game to work on a phone and with a keyboard, **so that** I can play in different environments.

Acceptance criteria:
- Layout remains usable at narrow mobile widths.
- Interactive controls are semantic buttons or form controls, keyboard-operable, and have visible focus styles.
- Status feedback is announced to assistive technology.
- Respect the system's reduced-motion preference and avoid flashing or graphic horror.

## Out of scope for the initial version
- Accounts, leaderboards, analytics, multiplayer, remote APIs, generated content, payment, or public deployment.
- Additional chapters, randomized puzzle answers, or a general-purpose game editor.

## Verification
Test a complete winning run, a wrong-code attempt followed by a correct solve, timer expiration and restart, refresh and continue behavior, locked-exit behavior, keyboard-only use, and a narrow mobile viewport. Confirm that the page loads and plays with the network disconnected.
