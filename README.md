![darknet](https://user-images.githubusercontent.com/13064391/224786876-6a65ab3e-3a40-4833-87bb-65a7840d8adb.png)

# Darknet

Darknet is an open source neural network framework written in C. It is fast, efficient, and supports CPU and GPU computation. 

I am using NVIDIA Quadro RTX 6000/8000 GPU. This is the first time, I am using darknet framework to develop deep learning model. Here, are the steps to follow to setup darknet framework.

# Resources 

darknet source code : https://github.com/pjreddie/darknet <br>
&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; https://github.com/AlexeyAB/darknet <br>
&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;https://github.com/arnoldfychen/darknet <br>
Installation guide :  https://pjreddie.com/darknet/install/ <br>
&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;https://docs.nvidia.com/deeplearning/cudnn/install-guide/index.html <br>
Supporting resources : https://github.com/pjreddie/darknet/issues/1347 <br>
&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;https://github.com/pjreddie/darknet/issues/1874 <br>
                      
# System setup

GPU : NVIDIA Quadro RTX 6000/8000<br>
CUDA toolkit version : 11.4<br>
Driver version : 470.57.02<br>
cuDNN version : 8.8.1.3<br>
OpenCV version : 4.2.0 <br>
Ubuntu : 20.04 <br>

# Steps 

1. Create virtual environment <br>
- Replace myenv with your environment name : virtualenv myenv   <br>
- Activate your virtual environment : source myenv/bin/activate   <br>
2. Install supporting packages <br>
- Install OpenCV library to handle Image IO tasks : sudo apt install libopencv-dev <br>
- Check version by 'pkg-config --modversion opencv4' command <br>
- Install CUDA toolkit according to your GPU  <br>
- Run 'nvidia-smi' command to check your CUDA version <br> 
- Download cuDNN package (linux tar.xz) according to CUDA version and install it. Documentation is given by cuDNN Documentation (Nvidia). <br>
- Verify installation using mnistCUDNN sample <br>
3. Install darknet <br>
- Download darknet using : git clone https://github.com/arnoldfychen/darknet.git <br>
- cd darknet <br>
- Replace the src/image_opencv.cpp file with given file (this will solve compatibility issues of darknet framework with OpenCV 4.0 package) <br>
- Replace Makefile with the given Makefile. Change NVCC=/usr/local/cuda/bin/nvcc by your nvcc path (this will solve error of unsupported gpu architecture) <br> 
- At the end test darknet, by running ./darknet imtest data/eagle.jpg

