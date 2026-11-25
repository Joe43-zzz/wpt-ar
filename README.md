# Wireless Power AR

A phone-browser AR app that draws the magnetic field, the energy flow and the lighting range on a real wireless-power demo (9 V single-transistor oscillator + two hand-wound coils + LED). No install: open the page, allow the camera.

## Files
- `index.html` – the AR app (A-Frame 1.3.0 + AR.js 3.4.5). Open `index.html#preview` for the 3D simulation without a camera.
- `sim.html` – 2D side-view simulation with sliders.
- `markers-wide-A4.pdf` – the two markers to print (4 cm black frame, 1.2 cm white border).
- `data/` – marker patterns and camera parameters used by AR.js.

## Hosting
The camera only works over HTTPS. Put this folder on GitHub Pages (or any HTTPS host) and open the address on the phone (Safari on iPhone/iPad, Chrome on Android).

## Testing without a camera
Open `index.html?test=<url of a 1280x960 camera frame>` on an HTTP server: the still frame stands in for the webcam and the whole pipeline (marker detection, threshold, coil finder, overlay) runs on it. Raw frames saved with **More → Save raw frame** are the right input.

## Placement
- Transmitter coil on the left, receiver coil on the right, both standing upright.
- Print `markers-wide-A4.pdf` at 100 % scale, cut along the dashed lines and keep the white border.
- Lay each marker flat in front of its own coil, the marked edge against the coil (Hiro for the transmitter). The coil, wires and shadows must not touch the black frame, or the phone cannot detect the marker.

## Use
1. First launch opens a 3-step setup: **Aim** (both markers ticked) → **Find the coils** (the app finds the copper and snaps the virtual coils onto the real ones; "Off? Adjust by hand" if needed) → **Calibrate** (optional).
2. Switch between **Field**, **Energy** and **Range** at the top. Tap the bottom bar for k, V₂ and the slow-motion scope. **3D** rotates the tracked setup.
3. **More (⋯)**: Tasks (five guided investigations), Modify (virtual resonant capacitor / relay coil), Run setup, Save raw frame, settings.
4. After both markers have been seen together once, one marker is enough.

## Model and calibration
- V₂ = k_cal × (M / L₁) × V₁, LED on above 1.8 V.
- V₁ = 18 V: the 9 V battery across one half of the centre-tapped 15+15-turn coil gives about 2 × 9 V across all 30 turns.
- k_cal = 2.3 by default, fitted to the bench test (LED still on at 5 cm, coils facing). It absorbs switching voltage peaks and model simplifications. Setup step 3 refits it: place the receiver where the real LED just goes out and tap **Here**.
