# Install-OpenCV-and-TF-2.2.0-on-RPi-3
Guia de comandos para instalar openCV y Tensorflow 2.2.0 en raspberry pi 3

# Mas info:
https://medium.com/analytics-vidhya/raspberry-pi-tensorflow-2-installation-and-yolo-v3-object-detection-549f2346a3ab

# dependencias generarel

sudo apt-get update
sudo apt-get dist-upgrade

sudo apt install python3-pip

sudo apt-get install -y libhdf5-dev libc-ares-dev libeigen3-dev gcc      gfortran python-dev libgfortran5 \
                          libatlas3-base libatlas-base-dev libopenblas-dev libopenblas-base libblas-dev \
                          liblapack-dev cython libatlas-base-dev openmpi-bin libopenmpi-dev python3-dev python3-venv
                          
# dependencias OpenCV

sudo apt-get install libjpeg-dev libtiff5-dev libjasper-dev libpng12-dev libavcodec-dev libavformat-dev libswscale-dev libv4l-dev libxvidcore-dev libx264-dev qt4-dev-tools libatlas-base-dev

pip3 install opencv-python==3.4.6.27

# install TF 2.2.0

sudo pip3 install keras_applications==1.0.8 --no-deps
sudo pip3 install keras_preprocessing==1.1.0 --no-deps
sudo pip3 install h5py>=2.9.0
sudo pip3 install pybind11
pip3 install -U --user six wheel mock
wget "https://raw.githubusercontent.com/PINTO0309/Tensorflow-bin/master/tensorflow-2.2.0-cp37-cp37m-linux_armv7l_download.sh"
sh ./tensorflow-2.2.0-cp37-cp37m-linux_armv7l_download.sh
sudo pip3 uninstall tensorflow
sudo -H pip3 install tensorflow-2.2.0-cp37-cp37m-linux_armv7l.whl

# comprobamos que este todo guay
import tensorflow as tf
print(tf.__version__)
