# ScanWisp

**Scan paper into a clean, searchable PDF, entirely in your browser. Nothing is uploaded.**

<https://scanwisp.com>

![ScanWisp](https://scanwisp.com/og-image.png)

## What it does

Point your camera at a document. ScanWisp finds the page edges, corrects the perspective, cleans up the image and turns it into a PDF. The PDF is built inside the browser tab and saved straight to your device.

No upload step, no account, no install.

## Why people use it

- **No upload.** There is no server to send the file to. The image is processed in the tab and written to local storage.
- **No account.** Open the URL and start scanning.
- **OCR is free with no page limit.** Searchable PDFs from page one to page five hundred.
- **Works offline.** Once the page has loaded, scanning and export keep working with the network off.
- **Any platform.** Windows, macOS, Linux, Android and iOS, in Chrome, Edge, Safari or Firefox.

## Features

| Capability | Detail |
|---|---|
| Edge detection | Automatic four-corner detection, with manual adjustment when it misses |
| Perspective correction | Warps a tilted phone photo back into a flat rectangle |
| Enhancement | Colour, grayscale, black and white, plus glare and shadow handling |
| OCR | On-device, 100+ languages, no page limit |
| Export | Image PDF, searchable PDF, plain text |
| Install | PWA, adds to the home screen and runs offline |

## What it does not do

No cloud storage, no cross-device sync, no batch auto-capture, no handwriting recognition. It is built for the dozen or so pages most people actually scan in a month, not for digitising an archive.

## How it works

Everything runs client side:

- **Edge detection and warping:** OpenCV.js
- **OCR:** RapidOCR models on ONNX Runtime Web, WebGPU with a WASM fallback
- **PDF assembly and invisible text layer:** pdf-lib and fontkit
- **Intermediate page storage:** OPFS, so large batches don't exhaust memory

No page image, PDF or recognised text is transmitted anywhere. The site uses cookieless Cloudflare Web Analytics for traffic counts.

## Status

The free scanner is live. A paid tier with heavier compression, batch tools and watermarking is planned. OCR stays free and unlimited.

This repository is for the project itself. The application source is not public.
