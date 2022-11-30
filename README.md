# OpenVINO Demos

This repo contains setup and instructions to run 3 OpenVINO demos with  OpenVINO 2021.4.2 LTS.

Following are the sections 
- Setup and Install OpenVINO 2021.4.2 LTS on Ubuntu 20.04
- Instructions to run demos.


## Setup and Install OpenVINO on Ubuntu 20.04

### Install prerequisites

```sh
sudo apt -y update

sudo apt install -y \
         build-essential \
         wget \
         vim \
         git \
         python3-pip \
         python3.8-venv \
         libgtk-3-0 \
         libgl1-mesa-glx
```


### [Optional] Install NEO driver for iGPU/dGPU. 
The Intel Graphics Compute Runtime for oneAPI Level Zero and OpenCL™ Driver is for running deep learning inference with OpenVINO on Intel iGPU/dGPU devices

```sh
wget https://raw.githubusercontent.com/openvinotoolkit/openvino/master/scripts/install_dependencies/install_NEO_OCL_driver.sh

chmod +x ./install_NEO_OCL_driver.sh

sudo ./install_NEO_OCL_driver.sh

sudo usermod -aG video $USER
sudo usermod -aG render $USER

# Verify install by running:
clinfo
```

### Install OpenVINO 2021.4.2 LTS.
- Install  OpenVINO 2021.4.2 LTS in a python virtual environment. See official instructions [HERE.](https://docs.openvino.ai/latest/openvino_docs_install_guides_install_dev_tools.html)
- Python3.8 is recommended. 

```sh
python3 -m venv openvino_env
source openvino_env/bin/activate

python -m pip install --upgrade pip

pip install openvino-dev==2021.4.2
```

### Setup Demo Code

```sh
git clone https://github.com/psakamoori/openvino_demos.git
cd openvino_demos

```

## Instructions for Demo 1: ID_person_demo

See more detailed `ID_person_demo` [README Here](https://github.com/psakamoori/openvino_demos/blob/master/ID_person_demo/face_recognition_demo/application/README.md)

```sh
# Assuming you activated openvino_env virtual env and inside openvino_demos directory.
(openvino_env) [ubuntu:~/openvino_demos]$

cd ID_person_demo/face_recognition_demo/application

python3 face_recognition_demo.py \
-m_fd ./intel/face-detection-retail-0004/FP32/face-detection-retail-0004.xml \
-m_lm ./intel/landmarks-regression-retail-0009/FP32/landmarks-regression-retail-0009.xml \
-m_reid ./intel/face-reidentification-retail-0095/FP32/face-reidentification-retail-0095.xml \
-d_fd CPU \
-d_lm CPU \
-d_reid CPU \
-i 0 

```

## Instructions for Demo 2: restricted_zone_notifier

See more detailed `restricted_zone_notifier` demo [README Here](https://github.com/psakamoori/openvino_demos/blob/master/restricted_zone_notifier/application/README.md)
```sh
# Assuming you activated openvino_env virtual env and inside openvino_demos directory.
(openvino_env) [ubuntu:~/openvino_demos]$

cd restricted_zone_notifier/application/

python3 restricted_zone_notifier.py \
-m ./intel/person-detection-retail-0013/FP32/person-detection-retail-0013.xml \
-d CPU

```

## Instructions for Demo 3: safety_gear_detector

See more detailed `safety_gear_detector` demo [README Here](https://github.com/psakamoori/openvino_demos/blob/master/safety_gear_detector/application/README.md)
```sh
# Assuming you activated openvino_env virtual env and inside openvino_demos directory.
(openvino_env) [ubuntu:~/openvino_demos]$

cd safety_gear_detector/application/

python3 safety_gear_detector.py \
-d CPU \
-m ../intel/person-detection-retail-0013/FP32/person-detection-retail-0013.xml \
-sm ../intel/worker-safety-mobilenet/FP32/worker_safety_mobilenet.xml

```

