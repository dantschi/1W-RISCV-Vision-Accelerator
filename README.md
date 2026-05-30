# Navigating the 1W Envelope: Area-Energy Trade-offs of Scalable RISC-V Systolic Arrays in Sky130

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Hardware](https://img.shields.io/badge/Hardware-Chisel_|_Verilog-orange.svg)]()
[![Node](https://img.shields.io/badge/Node-SkyWater_130nm-green.svg)]()

This repository contains the core artifacts, hardware extensions, and software evaluation scripts for our poster presented at RISC-V Summit Europe 2026. 

It serves as a clean landing page to explore our custom **SmartDMA** and **VisionControl** IP, as well as the quantization pipeline, without having to navigate a full Chipyard SoC environment.

## 🖼️ Poster & Presentation
You can find the high-resolution PDF of the poster in the [`/poster`](./poster) directory. 

*(Optional: Add a preview image of your poster here by uploading a `poster.png` and linking it: `![Poster Preview](./poster/poster.png)`)*

## 🚀 Abstract
Deploying high-performance AI inference (like real-time object detection or high-res vision) on micro-aerial vehicles requires a strict 1W power budget to preserve flight stability. Due to open-source hardware sovereignty trends, mature nodes like SkyWater 130nm are increasingly relevant. 

While systolic arrays maximize tensor efficiency, scaling them in a 130nm node leads to dramatic area-induced leakage and routing congestion. This work explores the vertical integration of the RISC-V Gemmini accelerator, scaling from 8x8 to 32x32 meshes, and introduces a **Zero-Copy L2-Handoff** mechanism to massively reduce active power.

## 📂 Repository Structure
To make our contributions easily accessible, this repository isolates our custom IP from the underlying framework:

* **`/hardware`**: Contains the Chisel/Verilog source code for our custom TileLink DMA (`SmartDMA`) and the memory-mapped trigger module (`VisionControl`).
* **`/software`**: Bare-metal C scripts used for the VisDrone and high-res vision evaluation, utilizing the diplomatic PLIC interrupts.
* **`/quantization`**: Python scripts (ONNX Runtime / Apache TVM) for the Post-Training Quantization (PTQ) pipeline down to INT8 (achieving a 74.75% memory footprint reduction).
* **`/poster`**: The LaTeX source code and final PDF of the poster.

## 🔗 Full Chipyard Environment
This artifact repository contains only the standalone modules for readability. For the complete, compilable SoC environment including the RISC-V Rocket Core, Gemmini, and all submodules, please visit our full development fork:
**[Link to your full Chipyard Fork on GitHub]**

## 📄 License
The hardware and software code in this repository is licensed under the [Apache License 2.0](LICENSE). The poster and its visual assets are provided under the [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/) license.