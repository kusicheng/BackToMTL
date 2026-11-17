# BackToMTL
This is an open-source project to extract text, translate the text, and automatically replace and redraw the image to fit the text. 

## Repository boundaries

BackToMTL owns the translation backend, image processing, OCR, detection, rendering, and related training code. [OpenMTL](https://github.com/kusicheng/openmtl) owns the frontend and user-facing application. [RagMTL](https://github.com/kusicheng/ragmtl) owns MAGRA retrieval and benchmarking.

These are separate repositories. Keep implementation in its owning repository; share functionality through explicit imports, supported APIs, or a deliberately abstracted shared component.

## Summary of pipeline
Unzip files -> model extracts text bubble boxes and segmentation masks -> feed into local/online LLM with specified json format -> check and validate response -> segmentation mask areas are erased and text bubbles are redrawn to fit text -> paste text in. 

## Model summary
Architecture used: YOLOv11.\
Base model: OCR-type from Kha-white.\
Additional validation: Mayocream - MangaOCR.\

## Current Status
Pipeline works and correctly extracts text and redraws image.\
Planned improvements in segmentation mask training by using more general images.\
No UI implemented: CLI is the way to interact. See main.py.\
UI planned in near future after OCR calibration and testing with general dataset and server rigs.\

Feel free to message for suggestions.
