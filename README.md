
# 🎨 Zynq Partial Reconfiguration/DFX: Real-Time Image Processing

A demonstration of **Dynamic Partial Reconfiguration (DPR)** on Xilinx Zynq-7000 SoC for real-time video processing. This project showcases the ability to dynamically swap image processing algorithms on-the-fly without interrupting the video stream.

## 🌟 Overview

This project implements a video processing pipeline where the image filter can be **reconfigured in real-time** using partial bitstreams. The system processes live video and applies different filters by loading partial configuration files through the Processor Configuration Access Port (PCAP).

### What is Partial Reconfiguration?

Partial Reconfiguration (PR) allows you to reconfigure a **portion of the FPGA** while the rest of the system continues to operate. This enables:
- 🔄 **Dynamic functionality switching** - Change algorithms without full system reset
- 💾 **Resource optimization** - Time-multiplex different functions in the same hardware area
- ⚡ **Reduced downtime** - Reconfigure in milliseconds while video keeps flowing
- 🔋 **Power efficiency** - Load only the processing logic you need

## 🎯 Features

### Static Region (Always Active)
- Video input pipeline (HDMI/Test Pattern)
- AXI4-Stream video processing infrastructure
- PS-PL interconnects and DMA
- Video output display controller
- ARM Cortex-A9 processor for control

### Reconfigurable Partition (Dynamic)
Three reconfigurable modules implementing different image filters:

#### 1️⃣ **Sharpen Filter**
- Enhances edges and fine details in the image
- Uses convolution kernel for edge enhancement
- Ideal for improving image clarity

#### 2️⃣ **Sobel Edge Detection**
- Detects edges in the image using Sobel operator
- Computes gradient magnitude in X and Y directions
- Produces edge map highlighting object boundaries

#### 3️⃣ **Static/Pass-Through**
- Passes video through without modification
- Useful as a baseline or bypass mode
- Minimal processing overhead

## 🏗️ Architecture

<img width="1883" height="925" alt="image" src="https://github.com/user-attachments/assets/451d8555-1c77-4e64-97cb-8590ae3b91c9" />
