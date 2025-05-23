# ORB\_SLAM3 Docker

> 🛠️ **Fork Notice**:
> This repository is forked from the official ORB-SLAM3 Docker setup ([see repository information](https://github.com/jahaniam/orbslam3_docker.git)).
> It has been slightly modified to help you quickly get started with ORB-SLAM3 in a Docker container.
> This setup includes an example using the EuRoC dataset to demonstrate how to compile and run the system.

These changes were made in response to multiple requests from students having difficulty setting up ORB-SLAM3 on their machines.
If you're working on a different SLAM method or setup, feel free to pursue your own direction—this is just a suggested starting point to help with **Assignment 1.3**.

---

### Available Docker Versions:

* CPU-based (Xorg / Nouveau display)
* NVIDIA CUDA-based (for systems with GPU support)

To check if you have the NVIDIA driver installed:

```
nvidia-smi
```

If that command works, you can use the CUDA version. Otherwise, use the CPU version.
Make sure you have [NVIDIA Docker Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html) installed for CUDA support.

---

## Compilation and Running

Follow these steps to compile ORB-SLAM3 and test it using the EuRoC MH01 dataset.

1. **Download sample dataset**:

   ```
   ./download_dataset_sample.sh
   ```

2. **Build the container** (choose one based on your setup):

   ```
   ./build_container_cpu.sh      # For CPU version
   ./build_container_cuda.sh     # For CUDA version
   ```

3. **Run a test example**:

   ```
   docker exec -it orbslam3 bash
   cd /ORB_SLAM3/Examples
   ./euroc_examples.sh
   ```

   ⏳ *It may take a few minutes to initialize.*

---

## Development Notes

You can edit the code using:

* **VSCode Remote - Containers** (recommended)
* **Sublime Text**, or any preferred editor:
