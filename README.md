OpenVINO Install on Ubuntu 20.04
------

## Install OpenVINO 2021.4.2 LTS
- Instal OpenVINO in a python virtual environment. See official instructions [HERE.](https://docs.openvino.ai/latest/openvino_docs_install_guides_install_dev_tools.html)
- Python3.8 is recommended. 

```sh
python3 -m venv openvino_env
source openvino_env/bin/activate

python -m pip install --upgrade pip
pip install openvino-dev==2021.4.2
```

## Install NEO driver for iGPU/dGPU
Install the Intel Graphics Compute Runtime for oneAPI Level Zero and OpenCL™ Driver for running deep learning inference with OpenVINO in Intel iGPU/dGPU.

```sh
wget https://raw.githubusercontent.com/openvinotoolkit/openvino/master/scripts/install_dependencies/install_NEO_OCL_driver.sh

chmod +x ./install_NEO_OCL_driver.sh

sudo ./install_NEO_OCL_driver.sh

sudo usermod -aG video $USER
sudo usermod -aG render $USER

# Verify install by running:
clinfo
```
## Refer below README.md to run listed demos

- [Instructions to run Safety_grear_detector] (https://github.com/psakamoori/openvino_demos/blob/master/safety_gear_detector/application/README.md)
- [Instructions to run ID_person_demo] (https://github.com/psakamoori/openvino_demos/blob/master/ID_person_demo/face_recognition_demo/README.md)
- [Instruction to run restricted_zone_notifier] (https://github.com/psakamoori/openvino_demos/blob/master/restricted_zone_notifier/application/README.md)
