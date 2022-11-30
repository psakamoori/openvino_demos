Safety Gear Detection:
------

## Command options:

```sh
usage: safety_gear_detector.py [-h] [-d DEVICE] -m MODEL [-sm SAFETY_MODEL] [-e CPU_EXTENSION] [-f FLAG]

optional arguments:
  -h, --help            show this help message and exit
  -d DEVICE, --device DEVICE
                        Specify the target device to infer on; CPU, GPU,FPGA, MYRIAD or HDDL is acceptable. Application willlook for a suitable plugin for device specified
                        (CPU by default)
  -m MODEL, --model MODEL
                        Path to an .xml file with a trained model's weights.
  -sm SAFETY_MODEL, --safety_model SAFETY_MODEL
                        Path to an .xml file with a trained model's weights.
  -e CPU_EXTENSION, --cpu_extension CPU_EXTENSION
                        MKLDNN (CPU)-targeted custom layers. Absolute path to a shared library with the kernels impl
  -f FLAG, --flag FLAG  sync or async
```

## Sample Command line:

```sh
(openvino_env) [ubuntu:~/openvino_demos/safety_gear_detector/application]$ 
python3 safety_gear_detector.py \
-d CPU \
-m ../intel/person-detection-retail-0013/FP32/person-detection-retail-0013.xml \
-sm ../intel/worker-safety-mobilenet/FP32/worker_safety_mobilenet.xml

```



