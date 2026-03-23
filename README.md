V4L2 USB Skeleton Driver

A Linux kernel-space driver that acts as a bridge between a USB device and the Video4Linux2 (V4L2) subsystem. This project provides a fundamental "skeleton" or template for developing full-featured USB video class (UVC) or custom video capture drivers.

🌟 Overview
This driver demonstrates how to:

Register a USB driver and a V4L2 device within the Linux kernel.

Handle USB Probe and Disconnect events for specific hardware (VID: 0x13d3, PID: 0x56c9).

Implement Bulk Endpoints (0x01 OUT, 0x82 IN) for raw data communication.

Utilize the Videobuf2 (VB2) framework for high-performance video buffer management (streaming).

Expose standard video device nodes (e.g., /dev/videoX) to userspace applications like VLC or FFmpeg.

🛠 Features
Standard V4L2 IOCTLs: Supports VIDIOC_QUERYCAP, S_FMT, G_STD, ENUM_INPUT, and more.

Format Support: Hardcoded for YUYV pixel format with support for both S-Video and HDMI timing configurations.

Buffer Management: Implements vb2_ops for queueing, preparing, and streaming video frames using vmalloc memory.

Dual Interface: Combines a custom character device interface (/dev/penX) for raw bulk messages and a V4L2 node for video streaming.
