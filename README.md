# MosaicEarth-Connector-Blender

Blender 3.6–4.2+ add-on & extension to publish WGS84-georeferenced .glb 3D scenes and 3D Gaussian Splats (.ply, .spz, .splat, .ksplat) to MosaicEarth.

## Releases & Ready-to-Install Downloads (`v0.3.0`)

- [`MosaicEarth-blender-0.3.0.zip`](https://github.com/nsicart/MosaicEarth-Connector-Blender/releases/download/v0.3.0/MosaicEarth-blender-0.3.0.zip)
- Also available directly from [MosaicEarth Desktop & Connectors (`app.mosaicearth.app/en/Desktop`)](https://app.mosaicearth.app/en/Desktop).

## Cloud & Local Workstation Endpoints

Every MosaicEarth connector speaks the open **MosaicEarth Synchronization Protocol v1** (chunked `4 MiB` resumable uploads + end-to-end `SHA-256` verification) and can connect to:

- **MosaicEarth Cloud** (default): `https://app.mosaicearth.app`
- **MosaicEarth Desktop (Local Workstation)**: `http://127.0.0.1:19771` (set `MOSAICEARTH_URL=http://127.0.0.1:19771` or select the endpoint in the connector UI).

## Usage & Setup

Download `MosaicEarth-blender-0.3.0.zip` from [Desktop & Connectors](https://app.mosaicearth.app/en/Desktop).

- **Blender 4.2 and later**: open **Edit → Preferences → Get Extensions → ⌄ (top-right) → Install from Disk…**, choose `MosaicEarth-blender-0.3.0.zip`, and enable **MosaicEarth Cloud & 3DGS Connector**.
- **Blender 3.6 – 4.1**: open **Edit → Preferences → Add-ons → Install…**, choose `MosaicEarth-blender-0.3.0.zip`, and enable the add-on.

Open the 3D Viewport sidebar (**N** → **MosaicEarth**):

1. Sign in with your MosaicEarth email and password (session tokens remain in memory only and are never saved inside `.blend` files).
2. Choose whether to export the visible scene or selected objects as binary glTF 2.0 (`.glb`), and/or attach an external **3D Gaussian Splat** (`.ply` with spherical harmonics, `.spz`, `.splat` or `.ksplat`).
3. Optionally enable **Attach WGS84 Georeference Anchor** (`Latitude`, `Longitude`, `Altitude`, `Heading`, `Pitch`, `Roll`, `Scale`) and select a target **MyEarth Project** + **4D Capture Date (`YYYY-MM-DD`)**.
4. Use **Pull & Import into Blender** to download any verified Cloud project or snapshot into a local directory and automatically import `.glb`, `.obj` or `.ply` models into a dedicated `MosaicEarth_<Name>` Collection.

Headless CLI usage is also included:

```bash
python3 -m mosaicearth_blender.core push --name "Quarry Mesh" --glb scene.glb --splat scene_3dgs.ply --lat 41.3874 --lon 2.1686 --survey-date 2026-11-12
```

## License

Released under **GNU Affero General Public License v3.0 or later (`AGPL-3.0-or-later`)** — see [`LICENSE`](./LICENSE).
