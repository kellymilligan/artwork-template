# Artwork Template

GitHub template for creating artwork using [canvas-sketch](https://github.com/mattdesl/canvas-sketch).

---

## Installation

Install the `canvas-sketch` CLI globally:

```
npm install canvas-sketch-cli -g
```

If streaming exports to GIF/MP4, install [ffmpeg](https://www.ffmpeg.org/), e.g. on Ubuntu:

```
sudo apt install ffmpeg
```

Install other optional dependencies (e.g. `canvas-sketch-util`)

```
npm install
```

---

## Usage

### 1a. Basic:

```
npm run sketch-to-png
```

Exports to a png still on save. An alias for:

```
canvas-sketch input/artwork.js --output=./output
```

Uses the `--output` flag to ensure file structure continuity between artworks

### 1b. With GIF/MP4 export:

```
npm run sketch-to-gif
or
npm run sketch-to-mp4
```

Enables the ability to export to streamed GIF (512px) or MP4 (1280px) files using `Ctrl` + `Shift` + `S`. An alias for:

```
canvas-sketch input/artwork.js --output=./output --stream [ gif --scale=512:-1 ]
```

Additional CLI config options can be found in the [canvas-sketch CLI Docs](https://github.com/mattdesl/canvas-sketch/blob/master/docs/cli.md)

### 2. Open

Open `localhost:9966` in the browser

### 3. Iteration

Use `canvas-sketch`'s git hashing feature to iterate on artwork:
`Ctrl` + `K` performs a `git add` and `git commit`, so that previous iterations can easily be accessed and re-run via their SHA

---

## Notes

- When using node to render canvas2d graphics, 2774.314mm @ 300dpi appears to be the absolute maximum size on either axis, even if non-square.
