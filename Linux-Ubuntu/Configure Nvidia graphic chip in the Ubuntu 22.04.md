# Configure Nvidia graphic chip in the Ubuntu 22.04

To activate your NVIDIA 4070 graphics card on Ubuntu 22.04.5, you can follow these steps. Ubuntu typically uses the Intel graphics by default, so we need to switch to the NVIDIA GPU for applications that require more power.

### Step-by-Step Tutorial:

1. **Update Your System**
   First, make sure your system is up-to-date:
   ```bash
   sudo apt update && sudo apt upgrade
   sudo apt dist-upgrade
   ```

2. **Install NVIDIA Drivers**
   - Ubuntu comes with a utility for managing proprietary drivers. Use the following command to search for available NVIDIA drivers:
     ```bash
     sudo ubuntu-drivers devices
     ```
   - This will display a list of recommended drivers for your NVIDIA GPU. Install the recommended driver:
     ```bash
     sudo ubuntu-drivers autoinstall
     ```
   - Alternatively, you can manually install the latest driver by using:
     ```bash
     sudo apt install nvidia-driver-<version>
     ```
     Replace `<version>` with the driver version recommended for your card (e.g., `nvidia-driver-525`).

3. **Reboot Your System**
   After installing the drivers, reboot your machine:
   ```bash
   sudo reboot
   ```

4. **Verify Installation**
   Once the system restarts, verify that the NVIDIA driver is working:
   ```bash
   nvidia-smi
   ```
   This command will show the NVIDIA GPU's status and the driver version in use.

5. **Configure Prime to Switch Between GPUs**
   To manage the switching between the Intel GPU and NVIDIA GPU, you can use `prime-select`. This tool helps you switch between the integrated Intel graphics and the discrete NVIDIA GPU.

   - **Switch to NVIDIA GPU:**
     ```bash
     sudo prime-select nvidia
     ```
   - **Switch to Intel GPU:**
     ```bash
     sudo prime-select intel
     ```

6. **Reboot Again**
   After switching, reboot your system again:
   ```bash
   sudo reboot
   ```

7. **Optional: Install NVIDIA Settings (For Configuration)**
   If you want to tweak your NVIDIA settings, you can install the `nvidia-settings` tool:
   ```bash
   sudo apt install nvidia-settings
   ```
   You can run this tool by typing `nvidia-settings` in the terminal to configure your GPU further.

---

Now your system should be able to utilize the NVIDIA 4070 when necessary. If you're using GPU-intensive applications (like games or certain software), they should automatically switch to the NVIDIA GPU when needed. If you want to check which GPU is active at any time, you can run `prime-select query`.