# Design: The Last Lantern

## Current implementation shape
The prototype is a dependency-free static page: `index.html` contains the accessible markup, responsive styles, and small client-side game state machine. It should remain runnable by opening the file directly in a browser. Do not introduce a build system unless a concrete feature needs one.

## State model
Track whether the game has started, the current room, inventory items, clue notes, puzzle/room flags, remaining seconds, and the win/timeout outcome. Persist only game progress in local storage. Validate saved state defensively and keep a fresh-start path available.

The essential sequence is: foyer discovery → unlock the study drawer with the clipping year → take the candle → light it in the cellar with a match → find the iron key → unlock the back door. Room descriptions and available actions should reflect the current state. The player may revisit accessible rooms without losing items or clues.

## Interaction and accessibility
Use native buttons and a labeled numeric text field for the year lock. Keep a polite live region for changing scene and action feedback. Provide clear text in addition to color for locked/current rooms and success/errors. Keep keyboard focus visible. Ensure controls wrap cleanly on mobile and avoid animation that conflicts with reduced-motion settings.

## Visual direction
Use a quiet, editorial Halloween atmosphere: near-black charcoal, restrained candle gold, muted green-gray, serif story headings, and small uppercase labels. Avoid external image, font, and script dependencies so the demo works offline. The CSS-built house illustration is decorative and hidden from assistive technology.

## Risks to review in Kiro
- Ensure action availability, copy, and puzzle flags have one source of truth; avoid duplicated state-transition logic.
- Confirm refresh/continue behavior doesn't reset or prematurely consume the timer.
- Ensure timeout and winning endings both stop the interval and permit a clean restart.
- Make the field notes and inventory clear after a player navigates between rooms.
- Test local-file browser behavior and mobile dimensions, not only the developer viewport.
