Restricted Zone Notifier
-----

## Command options:

```sh
usage: restricted_zone_notifier.py [-h] -m MODEL [-l CPU_EXTENSION] [-d DEVICE] [-th PROB_THRESHOLD] [-x POINTX] [-y POINTY] [-w WIDTH] [-ht HEIGHT] [-r RATE] [-f FLAG]

optional arguments:
  -h, --help            show this help message and exit
  -m MODEL, --model MODEL
                        Path to an .xml file with a trained model.
  -l CPU_EXTENSION, --cpu_extension CPU_EXTENSION
                        MKLDNN (CPU)-targeted custom layers. Absolute path to a shared library with the kernels impl.
  -d DEVICE, --device DEVICE
                        Specify the target device to infer on; CPU, GPU, FPGA, HDDL, MYRIAD is acceptable. To run with multiple devices use MULTI:<device1>,<device2>,etc.
                        Application will look for a suitable plugin for device specified(CPU by default)
  -th PROB_THRESHOLD, --prob_threshold PROB_THRESHOLD
                        Probability threshold for detections filtering
  -x POINTX, --pointx POINTX
                        X coordinate of the top left point of assembly area on camera feed.
  -y POINTY, --pointy POINTY
                        Y coordinate of the top left point of assembly area on camera feed.
  -w WIDTH, --width WIDTH
                        Width of the assembly area in pixels.
  -ht HEIGHT, --height HEIGHT
                        Height of the assembly area in pixels.
  -r RATE, --rate RATE  Number of seconds between data updates to MQTT server
  -f FLAG, --flag FLAG  sync or async

```

## Sample Command line:

```sh
application$  python3 restricted_zone_notifier.py -m ./intel/person-detection-retail-0013/FP32/person-detection-retail-0013.xml -d CPU
```
