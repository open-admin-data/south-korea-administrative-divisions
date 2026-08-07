# South Korea Administrative Divisions / 대한민국



## Overview

| Item | Details |
|------|---------|
| Province/City | 17 |
| District | 225 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-07 |
| Website | [openadmindata.org/kr](https://openadmindata.org/kr/) |
| API | [openadmindata.org/api/kr](https://openadmindata.org/api/kr/) |

## Browse by Province/City

| # | Province/City | Districts | Link |
|---|----|----|------|
| 1 | 충청북도 (North Chungcheong) | 13 | [Browse](divisions/north-chungcheong-kr01/) |
| 2 | 인천광역시 (Incheon) | 6 | [Browse](divisions/incheon-kr02/) |
| 3 | 강원도 (Gangwon) | 17 | [Browse](divisions/gangwon-kr03/) |
| 4 | 서울특별시 (Seoul) | 24 | [Browse](divisions/seoul-kr04/) |
| 5 | 경기도 (Gyeonggi) | 44 | [Browse](divisions/gyeonggi-kr05/) |
| 6 | 전라북도 (North Jeolla) | 15 | [Browse](divisions/north-jeolla-kr06/) |
| 7 | 광주광역시 (Gwangju) | 5 | [Browse](divisions/gwangju-kr07/) |
| 8 | 충청남도 (South Chungcheong) | 16 | [Browse](divisions/south-chungcheong-kr08/) |
| 9 | 대전광역시 (Daejeon) | 2 | [Browse](divisions/daejeon-kr09/) |
| 10 | 대구광역시 (Daegu) | 3 | [Browse](divisions/daegu-kr10/) |
| 11 | 경상남도 (South Gyeongsang) | 21 | [Browse](divisions/south-gyeongsang-kr11/) |
| 12 | 전라남도 (South Jeolla) | 22 | [Browse](divisions/south-jeolla-kr12/) |
| 13 | 부산광역시 (Busan) | 11 | [Browse](divisions/busan-kr13/) |
| 14 | 울산광역시 (Ulsan) | 1 | [Browse](divisions/ulsan-kr14/) |
| 15 | 경상북도 (North Gyeongsang) | 22 | [Browse](divisions/north-gyeongsang-kr15/) |
| 16 | 제주특별자치도 (Jeju) | 2 | [Browse](divisions/jeju-kr16/) |
| 17 | 세종특별자치시 (Sejong) | 1 | [Browse](divisions/sejong-kr17/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-province.json](data/all-province.json) | JSON | All 17 province/city records |
| [all-district.json](data/all-district.json) | JSON | All 225 district records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-province.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['district']} districts")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-province.json", "utf-8"));
console.log(`Total: ${data.length} province/citys`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=province/city, 2=district |
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
divisions/{province-slug}/
```

Districts are listed inline in each province/city's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-province/city links
- [Per-province/city data](docs/llms-full/) — Full data by province/city

## Citation

```
South Korea Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/south-korea-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
