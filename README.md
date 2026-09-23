# PasserBy

Meaningful connections, right around you.

PasserBy is a responsive, privacy-first campus friendship prototype built for SIT726 Task 8.2HD. Discover fictional nearby people through shared interests, request a conversation, and reveal fictional first names only after both people consent.

## Run locally

Open `prototype/index.html` in your browser. No installation, account, internet connection or build step is required.

Alternatively, with Python 3 installed, run this from the repository folder:

```sh
python3 -m http.server 8765 --bind 127.0.0.1 --directory prototype
```

Then visit http://127.0.0.1:8765/. Refreshing the page resets the demo.

## Features

- Profile setup with nickname, interests and an 18+ confirmation checkbox.
- Opt-in campus discovery with interest filtering and visibility controls.
- Chat requests with simulated acceptance or rejection.
- Anonymous chat with locally generated demonstration replies.
- Mutual-consent identity reveal, including withdrawal and decline.
- Local reporting, blocking and privacy controls.
- Simulated departure and 48-hour conversation expiry.
- Responsive layouts, keyboard navigation and dialog focus containment.

## Suggested walkthrough

1. Create your demo profile with two interests and confirm the age checkbox.
2. Opt into the fictional campus discovery pool.
3. Open Maple, send a chat request, then use the simulation control to accept it.
4. Send a message and observe the fictional reply.
5. Request identity reveal. The name stays hidden until you simulate the other person's agreement.
6. Simulate leaving the shared area, then advance 48 hours to expire the conversation.
7. Explore reporting, blocking, interest editing and discovery controls.

Some simulation controls appear below the chat; scroll down if needed.

## What is simulated?

The interface, validation, filters and state transitions work locally. People, campus presence, replies, identity consent from the other person and accelerated time are simulated.

This is **not a production social network**. There is no backend, actual geolocation, authentication, secure messaging, real moderation, verified identity or multi-user connection. Reports remain in a local session log and are not sent to a moderator. The age checkbox is not age verification. Fictional names are visible in the source code.

State exists only in memory and is cleared on refresh. Pausing discovery does not start the expiry timer; explicitly leaving the shared area does. Blocking deletes the conversation, and unblocking does not restore it. Do not enter personal or sensitive information.

## Repository structure

```text
prototype/
  index.html       Page structure
  styles.css       Branding and responsive styles
  app.js           Interactive prototype and simulated state
tests/
  smoke.cjs        Automated browser checks
README.md
```

## Optional automated tests

Install Node.js, then run from the repository folder:

```sh
npm install --no-save --package-lock=false playwright
npx playwright install chromium
node tests/smoke.cjs
```

Alternatively, set `BROWSER_PATH` to an installed Chromium-based browser executable. Tests create screenshots and a results file in `evidence/`, which is ignored by Git.

The supplied suite contains 24 functional checks. The original prototype passed these checks using Brave Chromium through Playwright. This is not participant testing, a security audit or a claim of full accessibility conformance. Real-device, cross-browser and participant testing remain future work.

## Design

The interface uses forest green (`#2F6B4F`), sage (`#7FAF8A`), mist (`#DDEFE2`), cream (`#F7F5EF`) and yellow (`#F2C94C`). System fonts and editable inline SVG illustrations keep the application self-contained. Branding continues the team's PasserBy concept.

Academic reports and demonstration videos are separate submission materials and are not included in this repository. Review and adapt the work in accordance with your unit's AI-assistance acknowledgement requirements.
