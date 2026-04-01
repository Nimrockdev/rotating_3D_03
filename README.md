# rotating_3D_03
# 🌍 Rotating 3D Globe

An animated 3D wireframe globe built with pure HTML5 Canvas and JavaScript — no libraries, no dependencies.

## Demo

Open `index.html` in any modern browser and the globe starts spinning immediately.

## Features

- 3D projection with correct visibility culling (back-face hidden)
- 12 latitude lines + 24 longitude meridians
- Equator highlighted
- 23.5° axial tilt (real Earth inclination)
- Smooth continuous rotation via `requestAnimationFrame`
- Subtle specular highlight for sphere depth
- Zero dependencies — single HTML file

## Usage

Just open the file in your browser:
```bash
open index.html
```

Or serve it locally:
```bash
npx serve .
```

## How it works

Each grid line is computed by projecting 3D spherical coordinates onto a 2D canvas using a custom projection function. Points are split into front-facing (z ≥ 0) and back-facing (z < 0) segments — only front-facing segments are drawn, giving the illusion of a solid sphere rotating in space.

The globe is tilted on its axis by applying a rotation matrix before projection:
```
y' = y·cos(tilt) - z·sin(tilt)
z' = y·sin(tilt) + z·cos(tilt)
```

## Tech stack

- HTML5 Canvas API
- Vanilla JavaScript
- CSS (background only)

## License

MIT
