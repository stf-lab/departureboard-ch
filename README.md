# 🚌 DepartureBoard CH

A lightweight, single-file real-time departure board for any public transport stop in Switzerland, built with plain HTML, CSS, and JavaScript. No build step, no dependencies.

![Dark theme](https://img.shields.io/badge/theme-dark-1a2236) ![Single file](https://img.shields.io/badge/single-file-brightgreen) ![Zero dependencies](https://img.shields.io/badge/dependencies-none-blue)

## Live

**[https://stf-lab.github.io/departureboard-ch/departureboard.html](https://stf-lab.github.io/departureboard-ch/departureboard.html)**

No installation needed — open the link and use it directly in your browser.

## Features

- **Real-time departures** — live countdowns with minute-by-minute updates (auto-refresh every 30 seconds)
- **Delay indicators** — distinguishes real-time data (`»`) from scheduled times (`*`), with delay badges (`+N min`)
- **Geolocation** — one tap to find and load your nearest stop
- **Station search** — search any stop in the Swiss public transport network
- **Line filters** — tap a line badge to filter departures by route
- **Expandable rows** — tap any row to reveal all upcoming departures for that line/direction
- **Persistent station** — your last selected stop is saved in `localStorage`
- **Mobile-ready** — responsive layout optimised for phones and tablet screens
- **PWA-capable** — can be added to the iOS home screen for an app-like experience

## Data Source

All departure data is fetched from the free, public **[transport.opendata.ch](https://transport.opendata.ch)** API. No API key is required.

Coverage includes the **entire Swiss public transport network**: SBB/CFF/FFS trains, PostBus, trams, lake boats, and all cantonal and urban bus operators (TPG, TPF, RBS, and many others). Any stop searchable in the SBB timetable works here.

## Default Station

The app defaults to **Ornex, Fruitière** (stop ID `1401767`). To change the default, edit this line near the top of the `<script>` block:

```js
let currentStation = { id: '1401767', name: 'Ornex, Fruitière' };
```

To find the ID for any stop, search for it in the app or query the API directly:

```
https://transport.opendata.ch/v1/locations?query=YOUR+STOP+NAME&type=station
```

## Customisation

The file is self-contained and straightforward to adapt:

| What | Where |
|---|---|
| Default stop | `currentStation` variable at the top of `<script>` |
| Refresh interval | `REFRESH_INTERVAL` constant (milliseconds) |
| Line colour coding | `LINE_HEX` object (add your own line numbers) |
| Destination abbreviations | `shortDestination()` function |
| Fonts | Google Fonts `<link>` in `<head>` |
| Colour theme | CSS variables in `:root` |

## Browser Support

Works in all modern browsers (Chrome, Firefox, Safari, Edge). Geolocation requires HTTPS — the live link above satisfies this automatically.

## License

MIT — do whatever you like with it.

## Credits

Departure data provided by [transport.opendata.ch](https://transport.opendata.ch), an open data initiative of Swiss public transport operators.
