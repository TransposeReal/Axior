# Axior

Axior is on a mission to democratize AI inference by delivering open, accessible AI chips and modules that anyone can integrate into edge or local compute infrastructures.  As large language models (LLMs) and multi-modal AI grow in capability, developers and enthusiasts have begun **clustering Mac Minis** to create on-premise inference farms—highlighting a surge in demand for affordable, scalable local AI hardware that avoids cloud latency and cost.  This niche remains underserved by major vendors, yet its potential is enormous: IDC projects the edge AI inference hardware market will exceed \$7 billion by 2027, driven by demand for private, low-latency AI deployments.

<img src="./Ai1_render.png" width="300">

## Axior Ai1 SoM

### Why Another AI Chip?
Despite advances in smartphone and server AI accelerators, there is **no truly open, modular AI SoM** optimized for inference at the edge.  Our first market targets **DIY local-AI enthusiasts**, then broadens to **consumer devices** capable of running quantized LLMs or vision/audio models—either standalone or as part of clusters.

### Target Segment
- **Phase 1:** Maker communities and researchers who cluster mini-servers for LLM inference.  
- **Phase 2:** Consumer-grade devices (smart speakers, robots, kiosks) with on-board AI.  

### SoM Overview
- **Form Factor:** Extended Jetson Xavier NX-compatible (75 × 45 mm)  
- **Edge Connector:** 260-pin SO-DIMM (mechanical drop-in)  
- **Memory:** Four vertical DDR5 SODIMM slots (1 ch per slot) → up to 512 GB (4×128 GB) shared by CPU/GPU/NPU  
- **I/O:** PCIe Gen4×4 (bifurcate to NVMe, Wi-Fi), USB 3.2×2, HDMI (DP++), 2× MIPI-CSI, GbE/10GbE, SDIO, GPIO/I²C/SPI/UART  
- **Clustering:** Carrier boards can host 1–4 SoMs, interconnected via PCIe switch or 10 GbE fabric  

### SoC Overview
- **Name:** Axior Ai1  
- **Process:** TSMC N7/N6 (~140 mm² die)  
- **CPU:** 8× Cortex-A78AE @ 2.2 GHz (ECC, ASIL-D)  
- **GPU:** Imagination PowerVR BXE-BX4-64 (64 clusters)  
- **NPU:** 4× Flex Logix InferX X1 tiles → 40 TOPS INT8  
- **Memory Ctrl:** Synopsys DDR5 4-ch + PHY (JEDEC-compliant, ECC)  
- **Other I/F:** PCIe 4 × 4, USB 3.2/2.0, eMMC 5.1, UFS 3.x, MIPI, RGMII, SDIO, secure boot (TrustZone + TPM)  
- **Power:** 5–12 V in, PMIC for 6 rails, ~3 W idle, 25 W peak  

### “Raspberry Pi of AI”
Just as the RK3588 has become the go-to SoC for low-cost Linux SBCs in China, **Ai1** aims to be the foundation chip for the next generation of open AI platforms—where every edge AI solution is “built on Axior,” from hobbyist clusters to commercial appliances.

## Detailed Specifications

### IP Cores & Architecture

| Subsystem      | IP Core / Vendor                          | Differentiator                                       |
|----------------|-------------------------------------------|------------------------------------------------------|
| CPU            | Cortex-A78AE ×8 (Arm)                     | ECC, safety, high-perf Linux                         |
| GPU            | PowerVR BXE-BX4-64 (Imagination)          | Vulkan 1.3, OpenCL 3.1                               |
| NPU            | InferX X1 ×4 (Flex Logix)                 | Modular tiles; scales to 40 TOPS INT8                |
| Memory Ctrl    | DDR5/DDR4 4-ch + PHY (Synopsys)           | 4 slots → up to 512 GB; future 1 TB possible          |
| PCIe           | Gen4 ×4 (Synopsys)                        | Bifurcation for NVMe, Wi-Fi, cluster fabric          |
| DSP            | HiFi 5 (Cadence)                          | Low-power audio/voice                               |
| NoC            | FlexNoC 5 (Arteris)                       | 512-bit coherent fabric                              |
| PMIC           | DA9063-L (Dialog)                         | 6 rails, DDR5 VPP, sequencing                        |
| Security       | CryptoCell-312 + SLB9670 (Arm/Infineon)    | Secure boot, TPM, TrustZone                         |

### Memory Capability

- **4× DDR5 UDIMM slots** (JEDEC)  
- **128 GB per slot** today → **512 GB total**  
- Unbuffered UDIMMs; future quad-rank or RDIMM modes approach 1 TB

### Clustering

- **Carrier board** options:
  1. **Single SoM** + SODIMMs, USB, Ethernet
  2. **Dual-SoM** mezzanine with PCIe switch backplane
  3. **4-SoM** micro-rack for midscale inference  
- **Interconnect:** 10 GbE or PCIe mesh; management via onboard CPU  

---

*Axior Ai1* empowers a new era of **open, scalable, on-device AI**, undercutting closed ecosystems and making local inference accessible to all.
