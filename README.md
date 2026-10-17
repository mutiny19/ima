# Indiana Off-Grid Comms

**Site: https://mutiny19.github.io/ima/**

A one-page starting point for getting on the mesh in Indiana, from the [Indiana Mesh](https://discord.gg/2uwyceSF37) community on Discord.

The site is a signpost, not an authority. It gives a new user the shortest path from a new radio to a first MeshCore message, then points to the people who maintain everything else: the official MeshCore docs, the official MeshCore Map, the regional groups, and the shared live-view tools. The one thing kept here is the [Indiana region settings](https://mutiny19.github.io/ima/advanced/) page for repeater owners.

## What's here

| Path | What |
|---|---|
| `index.html` | The page: official map centred on Indiana, four start steps, groups near you, live views, repeater links, other off-grid options |
| `advanced/` | Indiana region settings for MeshCore repeaters: pick counties on a map, get the commands |
| `assets/site.css` | Shared colours, fonts, header and footer |
| `meshcore/`, `live/` | Redirects for old links |
| `tools/check_links.py` | Weekly link check ([workflow](.github/workflows/links.yml)); opens an issue if an outside link breaks |

No build step, no data to refresh. The map and the radio preset are read live from MeshCore's own services when the page loads.

## Run it locally

Open `index.html`, or serve the folder:

```
python3 -m http.server 8000
```

## Suggest a change

[Open an issue](https://github.com/mutiny19/ima/issues/new/choose) for a broken link, a group that belongs on the page, or a correction. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[MIT](LICENSE)
