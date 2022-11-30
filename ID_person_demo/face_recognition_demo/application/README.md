Sample command line to run ID_person_demo
--------------

## Command options

```sh 
optional arguments:
  -h, --help            show this help message and exit

General:
  -i INPUT, --input INPUT
                        Required. An input to process. The input must be a single image, a folder of images, video file or camera id.
  --loop                Optional. Enable reading the input in a loop.
  -o OUTPUT, --output OUTPUT
                        Optional. Name of the output file(s) to save.
  -limit OUTPUT_LIMIT, --output_limit OUTPUT_LIMIT
                        Optional. Number of frames to store in output. If 0 is set, all frames are stored.
  --output_resolution OUTPUT_RESOLUTION
                        Optional. Specify the maximum output window resolution in (width x height) format. Example: 1280x720. Input frame size used by default.
  --no_show             Optional. Don't show output.
  --crop_size CROP_SIZE CROP_SIZE
                        Optional. Crop the input stream to this resolution.
  --match_algo {HUNGARIAN,MIN_DIST}
                        Optional. Algorithm for face matching. Default: HUNGARIAN.
  -u UTILIZATION_MONITORS, --utilization_monitors UTILIZATION_MONITORS
                        Optional. List of monitors to show initially.

Faces database:
  -fg FG                Optional. Path to the face images directory.
  --run_detector        Optional. Use Face Detection model to find faces on the face images, otherwise use full images.
  --allow_grow          Optional. Allow to grow faces gallery and to dump on disk. Available only if --no_show option is off.

Models:
  -m_fd M_FD            Required. Path to an .xml file with Face Detection model.
  -m_lm M_LM            Required. Path to an .xml file with Facial Landmarks Detection model.
  -m_reid M_REID        Required. Path to an .xml file with Face Reidentification model.
  --fd_input_size FD_INPUT_SIZE FD_INPUT_SIZE
                        Optional. Specify the input size of detection model for reshaping. Example: 500 700.

Inference options:
  -d_fd {CPU,GPU,MYRIAD,HETERO,HDDL}
                        Optional. Target device for Face Detection model. Default value is CPU.
  -d_lm {CPU,GPU,MYRIAD,HETERO,HDDL}
                        Optional. Target device for Facial Landmarks Detection model. Default value is CPU.
  -d_reid {CPU,GPU,MYRIAD,HETERO,HDDL}
                        Optional. Target device for Face Reidentification model. Default value is CPU.
  -l PATH, --cpu_lib PATH
                        Optional. For MKLDNN (CPU)-targeted custom layers, if any. Path to a shared library with custom layers implementations.
  -c PATH, --gpu_lib PATH
                        Optional. For clDNN (GPU)-targeted custom layers, if any. Path to the XML file with descriptions of the kernels.
  -v, --verbose         Optional. Be more verbose.
  -pc, --perf_stats     Optional. Output detailed per-layer performance stats.
  -t_fd [0..1]          Optional. Probability threshold for face detections.
  -t_id [0..1]          Optional. Cosine distance threshold between two vectors for face identification.
  -exp_r_fd NUMBER      Optional. Scaling ratio for bboxes passed to face recognition.
```


## Command line

```sh
(openvino_env) [ubuntu:~/openvino_demos/ID_person_demo/face_recognition_demo/application]$ 
python3 face_recognition_demo.py \
-m_fd ./intel/face-detection-retail-0004/FP32/face-detection-retail-0004.xml \
-m_lm ./intel/landmarks-regression-retail-0009/FP32/landmarks-regression-retail-0009.xml \
-m_reid ./intel/face-reidentification-retail-0095/FP32/face-reidentification-retail-0095.xml \
-d_fd CPU \
-d_lm CPU \
-d_reid CPU \
-i 0 
```

