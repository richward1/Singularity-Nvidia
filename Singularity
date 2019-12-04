Bootstrap: docker
From: debian:stretch

%setup
    	echo "Looking in directory '$SINGULARITY_ROOTFS' for /bin/sh"
	    if [ ! -x "$SINGULARITY_ROOTFS/bin/sh" ]; then
		echo "Hmm, this container does not have /bin/sh installed..."
		exit 1
	    fi
	exit 0

%post
	export NVIDIA_VER=NVIDIA-Linux-x86_64-435.21.run

	apt-get update
	apt-get -y upgrade
	apt-get -y install emacs vim nano \
	   lshw lsb-release bash-completion \
	   kmod iputils-ping net-tools \
	   wget curl
	
	wget http://us.download.nvidia.com/XFree86/Linux-x86_64/435.21/NVIDIA-Linux-x86_64-435.21.run -O /$NVIDIA_VER

	sh /$NVIDIA_VER -a -N --ui=none --no-kernel-module
	rm /$NVIDIA_VER

	wget https://sourceforge.net/projects/virtualgl/files/2.5.2/virtualgl_2.5.2_amd64.deb/download -O /tmp/virtualgl_2.5.2_amd64.deb
	apt-get -y install mesa-utils mesa-utils-extra x11-apps
	dpkg -i /tmp/virtualgl_2.5.2_amd64.deb
