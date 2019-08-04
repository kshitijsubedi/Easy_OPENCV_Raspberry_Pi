# Easily Install OpenCv in your Raspberry PI. No need to compile.

Tired of Those Tedious Compiling Steps to install OpenCV in Raspberry Pi ? Sometimes Pi just Reboot while Sometimes compilation error Occurs . Well, Here is the pre-compiled file for you for easy installation in no time.


Name: OpenCV
version: 4.1
Architecture : armhf
Target : Raspberry Pi
Python : 2 , 3
Status : Pre-Compiled

# No need to Compile Opencv for Serveral hours for your Raspberry Pi.

These are precompiled files and all you need is few terminal commands and you are ready to rock.

This will install OpenCV for both Python 2 and Python 3.

## STEPS
Make sure following packages are installed:

sudo apt install libtiff-dev zlib1g-dev libjpeg-dev libpng-dev libavcodec-dev 
sudo apt install libavformat-dev libswscale-dev libv4l-dev libxvidcore-dev libx264-dev

Steps:

  1. Open Terminal.
  2. Type :
      git clone https://github.com/kshitijsubedi/Easy_OPENCV_Raspberry_Pi
      cd Easy*
      
  3.    tar xfv opencv-4.1.0-armhf.tar.bz2
  4.    sudo mv opencv-4.1.0 /opt
  5.    sudo mv opencv.pc /usr/lib/arm-linux-gnueabihf/pkgconfig
  6.    echo 'export LD_LIBRARY_PATH=/opt/opencv-4.1.0/lib:$LD_LIBRARY_PATH' >> .bashrc
  7.    source .bashrc
  8.    sudo ln -s /opt/opencv-4.1.0/lib/python2.7/dist-packages/cv2 /usr/lib/python2.7/dist-packages/cv2
  9.    sudo ln -s /opt/opencv-4.1.0/lib/python3.7/dist-packages/cv2 /usr/lib/python3/dist-packages/cv2
  10. Close Terminal and Reopen
  11. Test :
      python
      import cv2
      exit()
    
# If You got any Error like ' libopencv_***.so.1.2 no such Directory or files .... '

Troubleshoot:
On Terminal :

    sudo nano /etc/ld.so.conf.d/opencv.conf
    Paste inside file : /opt/opencv-4.1.0/lib/
    Save and Exit nano.
    
 Run : sudo ldconfig -v

Re-Open Terminal

This should fix your probem.


