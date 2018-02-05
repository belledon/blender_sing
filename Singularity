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
    apt-get install -y  vim \
                        wget \
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
                        software-properties-common

    add-apt-repository ppa:jonathonf/python-3.6 && apt-get update
    apt-get install -y python3.6 \
		       python3.6-dev \
    
    mkdir /pip3.6 && cd /pip3.6
    wget https://bootstrap.pypa.io/get-pip.py
    python3.6 get-pip.py

    rm /usr/local/bin/python3
    rm /usr/local/bin/pip3
    ln -s /usr/bin/python3.6 /usr/local/bin/python3
    ln -s /usr/local/bin/pip /usr/local/bin/pip3
 

    apt-get clean


    pip3 install --upgrade pip
    pip3 install  multiprocess \
                            joblib \
                            scipy \
                            numpy \
                            transforms3d \
                            matplotlib


    rm -rf blender_fix
    git clone -b pypath https://github.com/belledon/blender_fix.git
    cd blender_fix
    chmod +x install.sh
    ./install.sh
