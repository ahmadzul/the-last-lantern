# Tasks: The Last Lantern

- [x] In the actual Kiro application, review the requirements and current prototype; make all subsequent code changes through Kiro and record the resulting work honestly.
  - Completed 2026-11-12. Full prototype reviewed; all subsequent changes made in Kiro.

- [x] Refactor game actions so each state transition has a single implementation; remove duplicated or unused action handlers.
  - Completed 2026-11-12. Replaced the dead `action()` helper, the unused closure-based `roomActions()`, and the button-text-keyed `handlers` map with a single `ACTIONS` registry (10 entries, keyed by stable IDs such as `foyer-matchbook`, `exit-turn-key`). Each entry declares `show()`, `disabled()`, and `run()` in one place. Added `renderActions(panel)` as the single wiring point and extracted `winGame()` to remove the inline win logic that was duplicated between the closure and the handlers map. HTML structure verified well-formed.

- [x] Verify the full clue chain: collect the foyer items, enter 1893, take the candle, light it with matches, find the iron key, and escape.
  - Completed 2026-11-12. Covered by Test 1 (33 assertions, all passing). Full sequence: matchbook → brass key → clipping (1893 note) → study code form → candle → cellar light → iron key → back door → win.

- [x] Verify helpful wrong-code feedback, locked-door behavior, and room revisits.
  - Completed 2026-11-12. Test 2: three wrong codes (0000, 1892, then 1893) confirm error feedback without progress loss. Test 3: `moveTo('exit')` blocked without iron key. Test 6: disabled state on `cellar-light-candle` with guard in handler. Room revisit logic (flags, descriptions) tested implicitly throughout the win-path test.

- [x] Verify timer start, timeout, winning state, refresh/continue behavior, and restart, including interval cleanup.
  - Completed 2026-11-12. Test 4: tick-to-zero sets `lost=true`, clears `started`, clears interval handle. `restart()` resets all fields to `freshState()`. Test 5: `save()`/`loadState()` round-trip restores room, inventory, flags, and seconds (clamped); `started` is `false` on resume; a saved won/lost game returns `freshState()`.
  - Node tests stubbed `setInterval` / `clearInterval` for state transitions. Real-time browser timing was also verified in Chromium by loading a saved one-second state, starting the game, and observing the timeout ending. Sub-second scheduling and duplicate-interval edge cases were inspected in code but not stress-tested.

- [ ] Complete the screen-reader and contrast audit.
  - Partially verified 2026-11-12 in Chromium: keyboard Tab/Enter starts the game; status/room-map semantics are present; reduced-motion preference is recognized; a 390×844 mobile viewport has no horizontal overflow; and the local-file game loads without external resources. The full escape, timeout, restart, and refresh/continue flows also passed browser checks. Actual screen-reader announcements and a measured contrast audit remain unverified.

- [ ] Ask the user before any public GitHub publication, YouTube upload, Devpost submission, paid service, or account creation/change.
  - Standing: no publication, deployment, upload, submission, account creation, or external network request has been made.
