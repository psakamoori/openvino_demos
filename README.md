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
