# Skyhook — Lawn Irrigation Topography & Site Model Author

Skyhook is a single-file, zero-backend, zero-build web application for interactive 2D/3D bare-earth LiDAR topography visualization, parcel cadastre inspection, hydraulic elevation pressure analysis, and site-model authoring for residential lawn irrigation planning.

## Features

### 1. 2D Topography & Aerial Imagery
- **LiDAR Elevation Grid**: Fetches bare-earth elevation data from the USGS 3DEP 1m LiDAR dynamic elevation service.
- **NAIP Aerial Base Layer**: Synchronized aerial imagery from USGS National Map ImageServer.
- **Chester County Parcel Boundaries**: Vector parcel boundary cadastre queries via PASDA.
- **Dynamic Contour Generation**: D3-computed contours (1ft, 2ft, 5ft intervals) with elevation labels and index line styling.
- **Interactive Drag & Pan**: 60fps pan and scroll-wheel zoom (100m, 200m, 400m radius).

### 2. 3D Watertight Diorama Viewer
- **Three.js Elevation Diorama**: Extruded watertight solid diorama block with real-world ground meters and $\cos(\text{lat})$ Mercator correction.
- **Vertical Exaggeration**: Real-time 1.0x–5.0x slider with dynamic normal recomputation.
- **Live North Compass**: Real-time camera-tracking orientation compass needle.
- **Watertight 3D Printing & CAD Export**: STL export (scaled to 180mm print size) and GLB export.

### 3. Site Model Authoring (Phase 1)
- **CAD Drawing Tools**: Polygon area drawing, rectangular box tool, exclusion polygons, exclusion utility lines, and vertex editor.
- **Vertex Snapping**: Automatic magnetic snapping to parcel boundaries and adjacent area vertices.
- **Auto-Dimming Contrast**: Automatically dims hillshade/contours during drawing for optimal aerial visibility.
- **Derived DEM Metrics**: Real-time polygon calculation of Area (sqft / acres), Perimeter (ft), Min/Max/Mean elevation (ft), Total relief ($\Delta Z$), Horn's gradient slope %, dominant aspect (N/NE/E/...), and static pressure spread ($\Delta Z \cdot 0.433\text{ psi}$).
- **Exclusion Zones & Buffers**: Custom buffer halos (ft) rendered live in both 2D SVG and 3D textured draping.
- **Water Infrastructure**: Well / municipal / cistern configuration with static pressure, safe yield, yield confidence, and service line parameters.
- **Manufacturer Heads Database (`heads.json`)**: Verified performance charts for Rain Bird 1800 MPR/VAN, Hunter MP Rotators, Hunter PGP/Ultra rotors, and Rain Bird 5000 rotors.
- **Continuous Advisory Validation**: Non-blocking diagnostics for out-of-bounds geometry, well yield alerts, and $>20\text{ft}$ relief warnings.
- **Local Persistence & Export**: JSON Schema validation on import/export and `localStorage` autosave.

## Running Locally

Serve the directory with any static HTTP server:

```bash
python3 -m http.server 9125
```

Open `http://localhost:9125` in your browser.
