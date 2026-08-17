# ARGUS Live Demo

ARGUS is an onboard image triage experiment proposed for ESA's Hera mission. ARGUS watches the camera feed, learns the scene as images arrive, and decides which images are worth downlinking.

## Live demo

https://georges.fyi/hera-argus/

Or open `index.html` locally in any modern browser. The page is fully self-contained: no server, no internet connection, and no installation needed. The 404 real Asteroid Framing Camera images and the complete detection algorithm are embedded in the file.

## What the demo shows

The detection algorithm runs live in the page. Every score is computed strictly frame by frame from the first image, exactly as onboard. The page shows:

- The current image with a live overlay: orange marks the pixels that surprise the detector given the images seen so far.
- A brightness histogram comparing the current image against the detector's memory, with the surprise mass filled orange.
- A side-by-side view of the current image, the most similar remembered image, and their difference.
- A score timeline across the full 7-hour sequence with alerts (red) and drift refreshes (yellow).
- A gallery of every image the detector decides to keep for downlink at the current settings.

## Things to try

- Press Play and watch the full sequence. Space pauses. Arrow keys step one frame.
- Click or drag on the timeline to jump anywhere in the sequence.
- Move the sensitivity sliders and watch the alerts, the kept-image gallery, and the downlink cost respond instantly. The whole simulation reruns from the first frame on every change.
- Lower the windowed-mean floor to see false alarms flood in. Press "Reset to defaults" to recover.
- Raise the drift-refresh threshold to see coverage gaps open up in the kept-image gallery.

## The headline result

At the default settings the detector keeps 9 images out of 404 (about 9 MB out of 420 MB) with zero false alarms across roughly 350 routine frames, while catching every genuine scene change in the sequence.
