<div align="center">

# Virtual Device Simulator for Embedded (VDS4E)

**Hardwareless Yocto Embedded Linux Application Development**

Develop and test embedded Linux applications on an x86_64 workstation without physical target hardware.

[![License](https://img.shields.io/badge/license-MIT%20OR%20Apache--2.0-blue.svg)](https://github.com/vds4e)
[![Documentation](https://img.shields.io/badge/docs-vds4e.dev-green.svg)](https://vds4e.dev)
[![Container Registry](https://img.shields.io/badge/GHCR-ghcr.io%2Fvds4e-orange.svg)](https://github.com/orgs/vds4e/packages)

</div>

---

## 🎯 What is VDS4E?

VDS4E allows embedded software engineers to build their application for an x86_64 target using their existing Yocto SDK/sysroot, and run it **unchanged** against real Linux userspace ABIs:

- **SPI:** `/dev/spidevX.Y` via CUSE
- **I2C:** `/dev/i2c-X` via CUSE (`i2cdetect`, `i2cget`, `i2cset`, `i2ctransfer` pass unmodified)
- **GPIO:** `/dev/gpiochipX` via CUSE (standard `libgpiod` tools work natively)
- **UART:** Kernel-assigned PTY `/dev/pts/N` (termios, `stty`)
- **Ethernet:** TAP interface `vdsN` (`ip`, `ping`, `tcpdump`)

No proprietary headers, no mock APIs, no code changes required in your production application.

---

## 🏛️ Ecosystem Repositories

| Repository | Purpose |
| :--- | :--- |
| **[vds4e/vds4e](https://github.com/vds4e/vds4e)** | Core simulation runtime, deterministic scheduler, server daemon, Web UI, and CLI |
| **[vds4e/devices](https://github.com/vds4e/devices)** | Official virtual device models (EEPROMs, NOR flash, sensor models, GPIO/UART peripherals) |
| **[vds4e/adapters](https://github.com/vds4e/adapters)** | Host Linux ABI adapters (CUSE, PTY, TAP interfaces) |
| **[vds4e/registry](https://github.com/vds4e/registry)** | Official device package index and automated OCI verification pipeline |

---

## 📦 Getting Device Packages

Browse and install verified device packages directly using the `vds-cli`:

```bash
# List all official packages in the organization
vds-cli package list vds4e

# Install a specific device model to your local project
vds-cli package install ghcr.io/vds4e/vds4e-atmel-at24c256:1.0.0
```

---

<div align="center">
  <sub>Maintained by the VDS4E Open Source Community • <a href="https://vds4e.dev">vds4e.dev</a></sub>
</div>
