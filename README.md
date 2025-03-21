﻿# Hairstyle-transfer-confyui

## Overview
This repository contains a ComfyUI setup for image generation and manipulation using Stable Diffusion models. The project is configured for systems with limited VRAM (4GB or less) and includes workflows for image inpainting and upscaling.

## System Requirements
- Windows OS
- NVIDIA GPU (project configured for NVIDIA GeForce GTX 1650 with 4GB VRAM)
- At least 32GB RAM

## Installation

### Quick Start
If you have an NVIDIA GPU:
```
run_nvidia_gpu.bat
```

For CPU-only mode (slower):
```
run_cpu.bat
```

### ComfyUI Manager
The project includes ComfyUI-Manager (v2.16.1) for easy installation of additional nodes and models. If you need to reinstall the manager:
```
install-manager-for-portable-version.bat
```

## Updating ComfyUI

### Update ComfyUI Code Only
```
update\update_comfyui.bat
```

### Update ComfyUI and Python Dependencies
Only run this if you're experiencing issues with Python dependencies:
```
update\update_comfyui_and_python_dependencies.bat
```

## Important Notes
- Make sure you have at least one model/checkpoint in: `ComfyUI\models\checkpoints`
- If no models are available, download Stable Diffusion 1.5 from: [HuggingFace](https://huggingface.co/runwayml/stable-diffusion-v1-5/blob/main/v1-5-pruned-emaonly.ckpt)
- If you see a red error in the UI, verify that checkpoints are properly installed

## Sharing Models Between UIs
1. In the ComfyUI directory, find `extra_model_paths.yaml.example`
2. Rename it to `extra_model_paths.yaml`
3. Edit the file with your preferred text editor to add paths to your existing model collections

## Included Workflow
The repository includes a sample workflow for image inpainting:
- Uses the photon_v1 model
- Configured for low VRAM usage
- Includes two-stage generation (initial inpainting followed by latent upscaling)
- Prompts can be customized in the "Prompt +" and "Prompt -" nodes

## Accessing the UI
When running ComfyUI, access the interface at:
```
http://127.0.0.1:8188
```

## Custom Nodes
The project includes several custom node collections:
- ComfyUI-Manager (for managing extensions and models)
- Efficiency Nodes
- Derfuu_ComfyUI_ModdedNodes
- Websocket Image Save

## Performance Notes
- The system is configured for low VRAM mode by default
- Each generation typically takes 90-150 seconds on the GTX 1650
- For faster processing, consider using a GPU with more VRAM and disabling low VRAM mode

## Troubleshooting
If you encounter issues:
1. Check the log files (comfyui.log and comfyui.prev.log) for error messages
2. Verify that all required models are properly installed
3. Try running in CPU mode if GPU issues persist
4. Ensure your NVIDIA drivers are up to date
