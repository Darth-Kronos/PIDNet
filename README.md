# Faster inference using Tensorrt Python!!

In this repo we use Torch-Tensorrt to convert PIDNet-S and PIDNet-M models to Tensorrt for faster inference.

## Usage
### 0. Setup
* Clone the official PIDNet repository and download the required model weight files.

### 1. Export the models to tensorrt
````bash
python tools/export.py --a pidnet-s --p ./pretrained_models/cityscapes/PIDNet_S_Cityscapes_test.pt --o ./pretrained_models/cityscapes/PIDNet_S_Cityscapes_test_trt.ts
````
### 2. Speed Measurement

* Measure the inference speed of PIDNet-S for Cityscapes:
````bash
python models/speed/pidnet_speed.py --a 'pidnet-s' --c 19 --r 1024 2048
````
* Measure the inference speed of PIDNet-S-trt for Cityscapes:
````bash
python models/speed/pidnet_speed.py --model ./pretrained_models/cityscapes/PIDNet_S_Cityscapes_test_trt.ts
````
### 4. Infer on Custom Videos

````bash
python tools/demo.py --model ./pretrained_models/cityscapes/PIDNet_S_Cityscapes_test_trt.ts --input ./path/to/sample/video
````

