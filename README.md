# GIMPS / VOL. 01 — WebAR

This project has three image targets, each mapped to its own plaque:

| Target index | Printed packaging image (to scan) | AR plaque (appears on camera) |
|---|---|---|
| 0 | `assets/packaging/gimp.png` | `assets/plaques/plaque-001.png` |
| 1 | `assets/packaging/pup.png` | `assets/plaques/plaque-002.png` |
| 2 | `assets/packaging/straight.png` | `assets/plaques/plaque-003.png` |

The plaque files are already filled with the supplied images. Replace them using the same filenames to update the AR content.

## Enable tracking

The printed packages share the same red layout, text and QR code, so the repeated areas can make image tracking mix them up. `assets/targets/` contains crops of the distinctive character artwork from the actual package images, excluding most of the repeated layout. The current `assets/targets.mind` has been compiled from these crops in the order below. MindAR can detect the cropped region while it appears as part of the full package in the camera.

1. Open the MindAR image target compiler: https://hiukim.github.io/mind-ar-js-doc/tools/compile/
2. Add `assets/targets/gimp-target.png`, `assets/targets/pup-target.png`, and `assets/targets/straight-target.png` in that exact order.
3. Export the compiled target file as `targets.mind` and replace `assets/targets.mind`.
4. Publish the updated site over HTTPS (e.g. GitHub Pages). Camera access requires browser permission.

The compiled target file must match the packaging artwork that will be scanned; replacing artwork does not update an existing `.mind` file. The website uses MindAR + A-Frame loaded from CDNs. AR placement is currently a flat plane and may need adjustment after testing against the physical packaging.


LOGO IMAGE
Replace assets/branding/gimps-logo.png with your own GIMPS wordmark image (keep the filename). This appears while the camera starts and as a small logo above the camera view. A transparent PNG is recommended.

## Camera selection

When the site opens, choose **USE REAR CAMERA** on a phone or **USE LAPTOP / FRONT CAMERA** to use a laptop webcam or a phone's front camera. The browser asks for camera permission after you choose. If a camera fails, the error screen lets you retry either option.

## Review notes
- Plaque planes preserve the supplied plaque image proportions (1488 × 2266) and are scaled to 2.625 × 3.996 MindAR units (50% larger than the previous 1.75 × 2.664 size). Adjust scale and placement after testing.
- The website has not been tested on a real phone; camera permission and target recognition must be verified after publishing.
- If two packaging designs are too visually similar, tracking may confuse them. Test all three individually.

## Troubleshooting
- If the wrong plaque appears intermittently, confirm the deployed `assets/targets.mind` was compiled from the three crop files in the exact order above. The target crops must match the artwork printed on the packages.
- Avoid glare, low light, motion blur and showing multiple packages at once while testing.
- The AR plaques are held back until a target has remained detected briefly, reducing quick flickers between targets.
- If the camera shows black, hard-refresh the published site and check camera permission, HTTPS, browser support and connection to the MindAR/A-Frame CDN.
- If no plaque appears, verify `assets/targets.mind` exists, is non-empty and was compiled from the artwork in the same order as the app mapping.


The three plaque files are the user-supplied original plaque images (uploaded 21 Oct 2026).
