# Project Microprocessor : Object Detection Models on the Raspberry Pi
<img src="Face Recognition/result.jpg"><img src="Face Recognition/result2.jpg">

## Details :memo:
- Object Detection ตรวจจับวัตถุด้วย Python และ TensorFlow ร่วมกับ Opencv 


## Setting up project: :computer:
```ruby
# Install dependencies
sudo apt-get update
sudo apt-get upgrade
sudo apt install cmake build-essential pkg-config git
sudo apt install libjpeg-dev libtiff-dev libjasper-dev libpng-dev libwebp-dev libopenexr-dev
sudo apt install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev libxvidcore-dev libx264-dev libdc1394-22-dev libgstreamer-plugins-base1.0-dev libgstreamer1.0-dev
sudo apt install libgtk-3-dev libqtgui4 libqtwebkit4 libqt4-test python3-pyqt5
sudo apt install libatlas-base-dev liblapacke-dev gfortran
sudo apt install libhdf5-dev libhdf5-103
sudo apt install python3-dev python3-pip python3-numpy
```
```ruby
# Preparing your Raspberry Pi for Compiling OpenCV
sudo nano /etc/dphys-swapfile
# Find >
CONF_SWAPSIZE=100
# Replace With >
CONF_SWAPSIZE=2048
Once changed, save the file by pressing CTRL+X followed by Y then Enter.

sudo systemctl restart dphys-swapfile
git clone https://github.com/opencv/opencv.git
git clone https://github.com/opencv/opencv_contrib.git
```
```ruby
# Compiling OpenCV on your Raspberry Pi
mkdir ~/opencv/build
cd ~/opencv/build

cmake -D CMAKE_BUILD_TYPE=RELEASE\
    -D CMAKE_INSTALL_PREFIX=/usr/local\
    -D OPENCV_EXTRA_MODULES_PATH=~/opencv_contrib/modules\
    -D ENABLE_NEON=ON\
    -D ENABLE_VFPV3=ON\
    -D BUILD_TESTS=OFF\
    -D INSTALL_PYTHON_EXAMPLES=OFF\
    -D OPENCV_ENABLE_NONFREE=ON\
    -D CMAKE_SHARED_LINKER_FLAGS=-latomic\
    -D BUILD_EXAMPLES=OFF ..
    
make -j$(nproc)
make
sudo make install
sudo ldconfig
```
```ruby
# Cleaning up after Compilation
sudo nano /etc/dphys-swapfile
# Find >
CONF_SWAPSIZE=2048
# Replace With >
CONF_SWAPSIZE=100
Once changed, save the file by pressing CTRL+X followed by Y then Enter.
sudo systemctl restart dphys-swapfile
```

## Testing installation: should print 'version'
```ruby
workon cv
python -c "import cv2; print(cv2.__version__)"
```

## Install TensorFlow and Set up TensorFlow Lite detection model
accessed here : https://github.com/EdjeElectronics/TensorFlow-Lite-Object-Detection-on-Android-and-Raspberry-Pi/blob/master/Raspberry_Pi_Guide.md

## Usage
```ruby
cd tflite1
source tflite1-env/bin/activate
