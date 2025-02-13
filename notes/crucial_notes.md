### NPU Driver Behavior

The NPU driver running in Linux does not directly interact with the NPU. Instead, it uses the **rpmsg mechanism** to notify the firmware running on Cortex‑M, which in turn directly communicates with the NPU. As a result, you will not see any code in the driver that performs direct I/O-mapped NPU register read/writes.

### Source Code and Image Considerations

- **OP-TEE Support:**  
  Zhengdianyuanzi’s source code and image do not include OP-TEE support because it isn’t configured in AT‑F.

- **DTB Compatibility:**  
  NXP’s DTB does not match the board’s specifications. This mismatch causes the built NPU firmware unable to work(because rpmsg memory region mismatch) and require further modifications.

- **Image Issues:**  
  When using NXP’s image, the board fails to detect USB, WiFi, or network cables—making file transfers impossible.

- **Proposed Solution:**  
  - Use Zhengdianyuanzi’s U-Boot combined with NXP’s `bl31.bin` (compiled TF-A) and `tee.bin` (compiled OP-TEE).  
  - Build `flash.bin` and use NXP’s `rootfs.tar.zst`.  
  - Burn the board with Zhengdianyuanzi’s Linux image and the corresponding DTB.  
  - Modify NXP’s ethosu_firmware rpmsg memory region to complement Zhengdianyuanzi’s DTB.

### i.MX93 Memory Access Control

The i.MX93 uses **TRDC** (Trusted Resource Domain Controller) instead of TZASC and TZPC. TRDC offers fine-grained access control, enabling the assignment of a memory region that is accessible only by the secure states of both Cortex‑A and Cortex‑M.
