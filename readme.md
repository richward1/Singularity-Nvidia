# Singularity Nvidia
Primary repository for an Ubuntu-based container with full NVidia hardware passthrough.

## Introduction
In order for this to work, you need to install the same version of driver that you're running on the host, into the container. Assuming you're running on a host with an NVidia GPU, you can find the driver version number with `nvidia-smi`.

The current driver version used in this project's Singularity file is `435.21`. If you're using the same driver version, then you can follow the rest of the guide under _Quick Start_.

## Quick Start

1. Clone the repo. `git clone https://github.com/richward1/Singularity-Nvidia`

2. Build the container from Singularityfile. `sudo singularity build nvidia.simg Singularity`

3. Run the container or shell into it. `singularity run nvidia.simg` _or_ `singularity shell nvidia.simg`

## Updating the NVidia Driver

I have written the Singularity file with a couple of environmental variables that will hopefully make it easier to update in the future. 

`$VER_NUM` contains the actual version number of the driver - in this case `435.21`.
`$NVIDIA_VER` is the full filename of the nvidia driver - in this case `NVIDIA-Linux-x86_64-$VER_NUM.run`

As it stands, the `435.21` driver is hosted in the US (http://us.download.nvidia.com/XFree86/Linux-x86_64/435.21/NVIDIA-Linux-x86_64-435.21.run). However, I have noticed that some other versions are hosted in the UK, so your milage may vary when swapping these values out.

## Author
Rich Ward
