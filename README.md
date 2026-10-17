# Indiana Off-Grid Comms

*Working name. From the [Indiana Mesh](https://discord.gg/2uwyceSF37) community on Discord. Work in progress.*

Quick-glance settings for off-grid communications in Indiana (MeshCore, Meshtastic, GMRS, ham radio, Reticulum) and links to each
protocol's official home.

## What's here

| Path | What |
|---|---|
| [`index.html`](index.html) | Home: statewide map (live NWS alerts, net schedule, live Kp), Indiana settings for each protocol, report form (opens a GitHub issue), support |
| [`meshcore/`](meshcore/) | **Get on the Indiana mesh:** first radio to first message, nearby groups, repeater region setup |
| [`advanced/`](advanced/) | **Indiana region settings** for MeshCore repeaters: pick counties on a map, get the commands |
| [`live/`](live/) | Where to watch live MeshCore traffic: Waev (preferred), OKI CoreScope, LetsMesh, MeshMapper, the MeshCore Map |
| [`assets/site.css`](assets/site.css) | Shared colors, fonts, header and footer |
| [`data/nets.json`](data/nets.json) | Net schedule that feeds the home page's Nets box (on air now, starting within the hour, next up) |
| [`data/settings/`](data/settings/) | Indiana's suggested settings, as data |
| [`tools/check_links.py`](tools/check_links.py) | Weekly link check ([workflow](.github/workflows/links.yml)); opens an issue if an outside link breaks |

Nothing from the mesh providers is cached here. Repeater positions and live traffic are links to the official MeshCore Map and the observer services; weather, Kp and the MeshCore radio preset load live in the browser.

## Run it locally

It's a static site with no build step. Open `index.html`, or serve the folder:

```
python3 -m http.server 8000
```

## Deploying

GitHub Pages from the repo root, branch `main`.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Settings changes, listings and corrections come in through the
[issue forms](https://github.com/mutiny19/ima/issues/new/choose).

## License

[MIT](LICENSE)
