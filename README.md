# Nearest Point Visualizer

An interactive coordinate-plane exercise for finding the point closest to a
chosen location. The page uses an animated, sci-fi tactical display.

## Run

Keep `nearest-point.html` and `nearest-point.js` in the same folder, then open
`nearest-point.html` in a modern browser. No packages, build step, or web server
are required.

## Use

1. Click the coordinate plane to set the origin.
2. Click again to add targets, or enter X and Y coordinates and select **Add
   target + fire**. Coordinates range from -10 to 10 and may include decimals.
3. Use the target log to edit or remove targets. The arrow buttons scroll to
   older targets or back to the latest one.
4. Select **Reset simulation** to clear the origin and all targets.

Setting the origin and adding each target plays a synthesized shot sound using
the browser's Web Audio API. Audio support and browser sound settings may affect
playback.

## How it works

The page calls `nearestPoint` from `nearest-point.js` to find the target with
the smallest Euclidean distance from the origin:

```text
distance = sqrt((x - locX)² + (y - locY)²)
```

If multiple targets are equally close, the first one added is selected. Target
colors show relative distance: the closest is green and the farthest is red.
If all targets are equally distant, they are all green.
