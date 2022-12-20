# NVIDIA_VRAM_KILL
NVIDIA_VRAM_KILL

    #!/bin/bash
    echo "KILL"
    for i in $(sudo lsof /dev/nvidia0 | grep python  | awk '{print $2}' | sort -u); do kill -9 $i; done
    nvidia-smi
