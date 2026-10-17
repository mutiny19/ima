# Indiana Off-Grid Comms

*Working name. From the [Indiana Mesh](https://discord.gg/2uwyceSF37) community on Discord. Work in progress.*

Quick-glance settings for off-grid communications in Indiana (MeshCore, Meshtastic, GMRS, ham radio, Reticulum) and links to each
protocol's official home.

## What's here

| Path | What |
|---|---|
| [`index.html`](index.html) | Home: statewide map (MeshCore repeaters from the nightly inventory, live NWS alerts, net schedule, live Kp), dashboard view, Indiana settings for each protocol, report form (opens a GitHub issue), support |
| [`meshcore/`](meshcore/) | **Get on the Indiana mesh:** first radio to first message, nearby groups, repeater region setup |
| [`advanced/`](advanced/) | **Indiana region settings** for MeshCore repeaters: pick counties on a map, get the commands |
| [`live/`](live/) | Where to watch live MeshCore traffic: Waev (preferred), OKI CoreScope, LetsMesh, MeshMapper, the MeshCore Map |
| [`assets/site.css`](assets/site.css) | Shared colors, fonts, header and footer |
| [`data/meshcore-nodes.json`](data/meshcore-nodes.json) | Repeaters on the map, refreshed nightly by [`tools/update_nodes.py`](tools/update_nodes.py) ([workflow](.github/workflows/nodes.yml)) from the official MeshCore Map feed. Repeaters only; personal nodes are counted, never plotted |
| [`data/in-counties.json`](data/in-counties.json) | Indiana county boundaries and population from the Census Bureau, refreshed yearly ([workflow](.github/workflows/reference.yml)); feeds the coverage view |
| [`data/nets.json`](data/nets.json) | Net schedule that feeds the home page's Nets box (on air now, starting within the hour, next up) |
| [`data/settings/`](data/settings/) | Indiana's suggested settings, as data |
| [`tools/check_links.py`](tools/check_links.py) | Weekly link check ([workflow](.github/workflows/links.yml)); opens an issue if an outside link breaks |

Data sources: the official MeshCore Map feed (nightly, repeaters only), the Census Bureau (yearly), and, live in the browser, the National Weather Service, NOAA SWPC and MeshCore's radio preset list. Live traffic is a link to Waev. If the nightly job stops, the map's source badge says so.

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
