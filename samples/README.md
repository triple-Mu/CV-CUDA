# CV-CUDA Samples

Sample applications to show how use some of CV-CUDA's functionalities.

## Pre-requisites

- Recommended linux distros:
    - Ubuntu >= 20.04 (tested with 20.04 and 22.04)
    - WSL2 with Ubuntu >= 20.04 (tested with 20.04)
- CUDA driver >= 11.7
- TensorRT == 8.5.2.2
- torch == 1.13.0
- torchvision == 0.14.0
- torchnvjpeg (https://github.com/itsliupeng/torchnvjpeg)

## Compile from Source

1. Copy the samples folder to the target directory

   ```
   cp -rf cvcuda/samples ~/
   cd ~/samples
   ```

1. Install the dependencies

   ```
   chmod a+x scripts/*.sh
   chmod a+x scripts/*.py
   ./scripts/install_dependencies.sh
   ```

1. Build the sample

   ```
   ./scripts/build_samples.sh
   ```

1. Run the sample. This script serializes generates a onnx files from the pytorch resnet model and converts to TensorRT engine which is loaded by the sample application.

   Note: The first run serializes the model which would make the inference slow.
   The maximum image dimensions needs to be set in the Main.cpp file if testing with different images.

   ```
   ./scripts/run_samples.sh
   ```
