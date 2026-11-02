# Service Area Analysis (geoskill-service-area-analysis)

> Network isochrone analysis + multi-facility service areas + coverage statistics, outputting service area GeoJSON.

---

## 1. Overview

Computes facility service areas (isochrones) from a network graph: Dijkstra computes network travel time for each facility, service areas are delineated by time thresholds, with support for multi-facility overlay, nearest-facility assignment and multi-threshold coverage statistics.

## 3. Quick Start

```bash
pip install -r requirements.txt
python geoskill-service-area-analysis.py --bbox 116 39 117 40 --synthetic --output-dir ./out
```

## 4. CLI Parameters

Run `python <skill>.py --help` for the full list. Common parameters:

| Parameter | Type | Description |
|---|---|---|
| `--bbox` | `float[4]` | WGS84 bounding box `min_lon min_lat max_lon max_lat` |
| `--input` | `path` | Local input file (GeoJSON/GeoTIFF/etc.) |
| `--output-dir` | `path` | Output directory (default `./output`) |
| `--synthetic` | `flag` | Use synthetic data instead of real input |
| `--quiet` | `flag` | Suppress non-essential stdout |

## 5. Input / Output

| File | Format | Description |
|---|---|---|
| `service_area.geojson` | GeoTIFF/GeoJSON/JSON | Primary output |
| `service_area_stats.json` | GeoTIFF/GeoJSON/JSON | Primary output |
| `output-manifest.json` | JSON | Run manifest |

## 6. Technical Principle

- Multi-source Dijkstra isochrones
- Nearest-facility assignment
- Multi-threshold coverage demand statistics

## 8. License

MIT License. See [`LICENSE`](./LICENSE) for full text.

---

> 中文完整版：[references/SKILL.zh-CN.md](references/SKILL.zh-CN.md)
