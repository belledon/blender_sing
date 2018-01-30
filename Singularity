bootstrap: docker
from: ubuntu:16.04


# %runscript
#     echo "SINGULARITY RUNSCRIPT"
#     echo "Arguments received: $*"
#     exec /usr/bin/python3 "$@"


%post
    apt-get update && apt-get -y install locales
    # locale-gen C.UTF-8
    locale-gen en_US.UTF-8
    # export LANG=C.UTF-8
    # export LC_ALL=C
    apt-get install -y  wget \
                        bzip2 \
                        ca-certificates \
                        libglib2.0-0 \
                        libxext6 \
                        libsm6 \
                        libxrender1 \
                        git \
                        cmake \
                        g++ \
                        xvfb \
                        libyaml-cpp-dev \
                        python3-dev \
                        python3-pip \
                        software-properties-common

    apt-get clean


    python3 -m pip install --upgrade pip
    python3 -m pip install  multiprocess \
                            joblib \
                            scipy \
                            numpy \
                            transforms3d \
                            matplotlib


    git clone https://github.com/belledon/blender_fix.git
    cd blender_fix
    chmod +x install.sh
    ./install.sh
