# Fashion Camera Library

A static page with 35 camera angle prompts for AI fashion photoshoots, grouped by height, framing, orientation, position, lens and aperture. **Create your own angle** lets visitors upload a reference photo, pick the closest angle from the library and copy that prompt with a "References:" line that tells Nano Banana Pro to match the photo's camera. It runs in the browser; the photo is never uploaded. No server code, no API keys.

```
public/index.html   the page (the angle data is inline in the ANGLES array)
public/img/         35 angle images at 2048px WebP, named by code (H01.webp …)
public/thumb/       small JPEG thumbnails for the angle picker
public/og.jpg       share preview for LinkedIn and X
```

Source: the Pletor workflow "PHOTO CAMERA ANGLES LIBRARY" (https://app.pletor.ai/flow/a34ef2ac-f4c3-4d8c-874f-27b818464d24).

## Deploy

Pushes to `main` on GitHub (raphaelguilhem-dot/fashion-camera-library) deploy to the Vercel project `fashion-camera-library`. Manual deploy:

```bash
npx vercel@60.1.3 deploy --prod
```

## Updating the library

Edit the `ANGLES` array in `public/index.html`. The Camera section of every prompt starts with the shared `RESHOOT` sentence, which is kept out of the data. Add the image as `public/img/<code>.webp` and a thumbnail as `public/thumb/<code>.jpg`:

```bash
sips -Z 360 -s format jpeg -s formatOptions 72 public/img/H01.webp --out public/thumb/H01.jpg
```

O06 is named "Steep High Angle" here; the workflow node is called "Top-Lit Vertical".
