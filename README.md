# Cape Verde Administrative Divisions / Cabo Verde



## Overview

| Item | Details |
|------|---------|
| Municipality | 22 |
| Parish | 32 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-06-01 |
| Website | [openadmindata.org/cv](https://openadmindata.org/cv/) |
| API | [openadmindata.org/api/cv](https://openadmindata.org/api/cv/) |

## Browse by Municipality

| # | Municipality | Parishs | Link |
|---|----|----|------|
| 1 | Boa Vista | 2 | [Browse](divisions/boa-vista-cv01/) |
| 2 | Brava | 2 | [Browse](divisions/brava-cv02/) |
| 3 | Maio | 1 | [Browse](divisions/maio-cv03/) |
| 4 | Mosteiros | 1 | [Browse](divisions/mosteiros-cv04/) |
| 5 | Paul | 1 | [Browse](divisions/paul-cv05/) |
| 6 | Porto Novo | 2 | [Browse](divisions/porto-novo-cv06/) |
| 7 | Praia | 1 | [Browse](divisions/praia-cv07/) |
| 8 | Ribeira Brava | 2 | [Browse](divisions/ribeira-brava-cv08/) |
| 9 | Ribeira Grande | 4 | [Browse](divisions/ribeira-grande-cv09/) |
| 10 | Ribeira Grande de Santiago | 2 | [Browse](divisions/ribeira-grande-de-santiago-cv10/) |
| 11 | Sal | 1 | [Browse](divisions/sal-cv11/) |
| 12 | Santa Catarina | 1 | [Browse](divisions/santa-catarina-cv12/) |
| 13 | Santa Catarina do Fogo | 1 | [Browse](divisions/santa-catarina-do-fogo-cv13/) |
| 14 | Santa Cruz | 1 | [Browse](divisions/santa-cruz-cv14/) |
| 15 | Sao Domingos | 2 | [Browse](divisions/sao-domingos-cv15/) |
| 16 | Sao Filipe | 2 | [Browse](divisions/sao-filipe-cv16/) |
| 17 | Sao Lourenco dos Orgaos | 1 | [Browse](divisions/sao-lourenco-dos-orgaos-cv17/) |
| 18 | Sao Miguel | 1 | [Browse](divisions/sao-miguel-cv18/) |
| 19 | Sao Salvador do Mundo | 1 | [Browse](divisions/sao-salvador-do-mundo-cv19/) |
| 20 | Sao Vicente | 1 | [Browse](divisions/sao-vicente-cv20/) |
| 21 | Tarrafal | 1 | [Browse](divisions/tarrafal-cv21/) |
| 22 | Tarrafal de Sao Nicolau | 1 | [Browse](divisions/tarrafal-de-sao-nicolau-cv22/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-municipality.json](data/all-municipality.json) | JSON | All 22 municipality records |
| [all-parish.json](data/all-parish.json) | JSON | All 32 parish records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-municipality.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['parish']} parishs")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-municipality.json", "utf-8"));
console.log(`Total: ${data.length} municipalitys`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=municipality, 2=parish |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{municipality-slug}/
```

Parishs are listed inline in each municipality's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-municipality links
- [Per-municipality data](docs/llms-full/) — Full data by municipality

## Citation

```
Cape Verde Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/cape-verde-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
