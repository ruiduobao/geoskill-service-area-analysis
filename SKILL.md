---
name: geoskill-service-area-analysis
description: '网络等时圈分析+多设施服务区+覆盖统计，输出服务区GeoJSON'
---

# 服务区分析 | Service Area Analysis

Computes facility service areas (isochrones) from a network graph: for each facility, Dijkstra computes network travel times, and service areas are delineated by time thresholds. Supports multi-facility overlay, nearest-facility assignment, and multi-threshold coverage statistics.

## Core Algorithm / 核心算法

- Multi-source Dijkstra isochrones
- Nearest-facility assignment
- Multi-threshold coverage demand statistics

## Dependencies / 依赖

```bash
pip install numpy rasterio scipy geopandas shapely
```

## Usage / 使用方法

### Example 1 (Synthetic Data, Offline)

```bash
python geoskill-service-area-analysis.py --bbox 116.0 39.0 117.0 40.0 --synthetic --output-dir ./out
```

### Example 2 (Specified Region + Silent Mode)

```bash
python geoskill-service-area-analysis.py --bbox 121.0 31.0 122.0 32.0 --synthetic --output-dir ./out2 --quiet
```

### Example 3 (Real Input)

```bash
python geoskill-service-area-analysis.py --input <your data file> --output-dir ./out3
```

### Example 4 (Minimal-Region Boundary Test)

```bash
python geoskill-service-area-analysis.py --bbox 116.39 39.90 116.40 39.91 --synthetic --output-dir ./out4 --quiet
```

## Output / 输出

| File | Format | Description |
|---|---|---|
| `service_area.geojson` | GeoTIFF/GeoJSON/JSON | Primary output |
| `service_area_stats.json` | GeoTIFF/GeoJSON/JSON | Primary output |
| `output-manifest.json` | JSON | Run manifest |

## Data Source / 数据源 / Source

- Synthetic mode: locally generates physically consistent simulated data, with no external data source.
- Real mode: reads local input files, with no network requests.

## Privacy / 隐私声明 / Privacy

- Runs fully offline by default and makes no network requests.
- `--synthetic` mode reads no external data.
- All computation is done locally; no user data is uploaded.

## License / License

MIT

---

> 中文完整版：需要时再读 [references/SKILL.zh-CN.md](references/SKILL.zh-CN.md)，不要默认全量加载。
