# MapVision Traffic Vision Studio

Demo: https://xulytiengviet.github.io/mapvision/

Browser-only traffic movement simulation inspired by DynamicMap Studio and the coordinate-first tracking pipeline of the existing rock-climbing modules.

## Features
- 1–50 identifiable animated neon vehicles on multiple normalized 2D polylines.
- Adjustable playback, vehicle count and geofence dwell threshold.
- Zone-entry/exit hysteresis and time-based stop confirmation.
- Vehicle list, simulated speed, completed trips, stop events.
- Import/export of route JSON, event CSV, analysis JSON and image PNG.
- Fully static: deploy the root `index.html` with GitHub Pages, branch main, root.

## Important scope
This is a **synthetic visualization and simulation**, not camera-based vehicle tracking. Road layouts, vehicle speeds (km/h display), zones and road coordinates are illustrative, not georeferenced or physically calibrated. No SAM, ViTPose, homography, real image segmentation or GPS input is executed here. To process real videos, add a separate OpenCV/SAM/vehicle-detection pipeline, calibrated camera/geo-registration, per-track detections and real-world distance scales.

The original upstream research modules retain their Apache-2.0 terms. The new standalone browser demo is MIT © 2026 Long Ngo; see `TRAFFIC_VISION_LICENSE.md`.
