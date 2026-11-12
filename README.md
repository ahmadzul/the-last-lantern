# The Last Lantern

A small, atmospheric browser escape room set in Blackthorn House. Find useful objects, follow the clues, solve a four-digit lock, light the cellar candle, and reach the back door before the five-minute timer runs out.

## Play locally

Open `index.html` in a modern browser. There is no install, build step, account, or network connection required. Game progress is saved in that browser's local storage; choose **Start over** to clear the saved game.

## What’s in the prototype

- Three explorable rooms and a locked exit.
- Inventory, field notes, and a clue-led four-digit lock.
- A five-minute countdown, win and timeout endings, and a restartable game loop.
- Responsive layout, keyboard-operable controls, visible focus treatment, and reduced-motion support.

## Kiro use and verification

The initial game starter and the `.kiro` planning/specification files were created manually before Kiro was used. Later, Kiro CLI was installed and authenticated, then used to validate save data, refactor game action logic, fix a restart/save edge case, and improve keyboard focus, retention of text entered while the timer runs, and text contrast. This is a manually started prototype with Kiro-assisted development—not a project authored entirely by Kiro. See [KIRO_USAGE.md](KIRO_USAGE.md) for the fuller disclosure and testing limits.

Reported checks during development included 64 Node.js checks and 20 Chromium checks. Browser scenarios covered keyboard game flow, win and timeout behavior, and contrast checks with a minimum measured ratio of 4.67:1. Screen-reader behavior has not been tested with NVDA or VoiceOver.

## Project status

This is a local browser prototype published as source in this public repository. No deployed demo, uploaded video, or hackathon submission is included.

## License

Released under the [MIT License](LICENSE).
