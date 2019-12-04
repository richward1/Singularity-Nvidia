# Singularity Alpine NoVNC
Primary repository for an Ubuntu-based container with full NVidia hardware passthrough.

## Usage

Clone the repo.
```
git clone https://github.com/richward1/Singularity-Nvidia
```

Build the container from Singularityfile.
```
sudo singularity build nvidia.simg Singularity
```

Run the container  
```
singularity run nvidia.simg
```

## Author
Rich Ward
