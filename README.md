# Timezone Converter

A single-file world clock and meeting planner. Track the current time across any set of zones, then pick a moment to see it everywhere at once and find the working-hours overlap for a call.

**Live demo:** https://0xelitesystem.github.io/timezone-converter/

## Use

1. Open the page. It starts with your local zone plus a few common ones (New York, London, Tokyo, UTC).
2. Add zones with the search box. It accepts any IANA name (for example `Europe/Berlin` or `Asia/Kolkata`) and autocompletes from the full list your browser ships.
3. Pick a reference zone. This is the zone whose clock you set when planning a meeting.
4. Set the meeting time with the datetime field or drag the slider. Every zone updates to the matching local time, with a `+1 day` or `-1 day` badge when the date rolls over.
5. Read the overlap strip under each zone. Each column is the same absolute moment across all rows, so a vertical slice shows what time it is everywhere at once. Working hours are shaded, and the red marker is the moment you selected. Click any cell to jump to that hour.
6. Switch between 24 hour and 12 hour clocks, and set your working-hours window (default 9 to 17 local).
7. "Copy summary" puts a plain-text rundown of the selected time in every zone on your clipboard, ready to paste into a message.

Your zone list and settings are remembered in the browser between visits.

## Why this exists

Most timezone and meeting-planner sites bury a simple calculation under ads, sign-in walls, and third-party trackers, and many still get daylight saving wrong on the edges. This is one HTML file with no build step, no dependencies, and no network calls. It leans on the IANA time zone database that every modern browser already ships, so daylight saving and historical offset changes are handled correctly without shipping a megabyte of tables. Read the source top to bottom in a couple of minutes, host it anywhere, and it stays MIT licensed.

## Privacy

Everything runs in your browser. There is no server, no analytics, and no network request of any kind. Your zone list and preferences are stored only in your browser's local storage on your own machine and never leave it. The clipboard summary is written locally by you when you press the button.

## Run locally

```
git clone https://github.com/0xelitesystem/timezone-converter.git
cd timezone-converter
```

Then open `index.html` in any browser, or serve the folder:

```
python -m http.server 8000
```

and visit `http://localhost:8000/`.

## Build

There is no build. It is a single `index.html` with inline CSS and JavaScript and no dependencies. Edit the file and reload.

## More

Part of a catalog of single-file browser tools and plain-language references, all MIT licensed and dependency-free: [0xelitesystem.github.io](https://0xelitesystem.github.io/). Built by [elitesystem.ai](https://elitesystem.ai).

## License

MIT. See [LICENSE](LICENSE).

## Related

- [unix-timestamp-converter](https://github.com/0xelitesystem/unix-timestamp-converter) - convert epoch seconds and milliseconds to and from human-readable dates.
- [jwt-inspector](https://github.com/0xelitesystem/jwt-inspector) - decode and inspect JSON Web Tokens locally.
