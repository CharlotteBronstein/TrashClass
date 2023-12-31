# Trash Classifier

This project can tell the difference between landfill and recycling.

<img width="815" alt="Screenshot 2023-07-23 at 9 14 52 PM" src="https://github.com/CharlotteBronstein/TrashClass/assets/140207456/c08a5c67-ee50-454a-8914-6cde100d42e5">

## The Algorithm

This algorithm works by using a trained classification network and retraining it to recognize the difference between recycling and landfill. Having this pre-trained classification network to build off of makes the algorithm more accurate in less training than building it from scratch would.

## Running this project

1. Download resnet18.onnx and labels.txt from this repository onto your Jetson Nano
2. Run these commands in the command line to clone the Jetson-Inference project:

   sudo apt-get update
   
   sudo apt-get install git cmake
   
   git clone --recursive https://github.com/dusty-nv/jetson-inference
   
   cd jetson-inference
   
   git submodule update --init
   
   sudo apt-get install libpython3-dev python3-numpy
   
   mkdir build
   
   cd build
   
   cmake ../
   
   make
   
   sudo make install
   
   sudo ldconfig

4. Upload a photo onto your nano that you want the network to classify
5. Run the this command in the command line:

imagenet.py --model=path/to/resnet18.onnx --input_blob=input_0 --output_blob=output_0 labels=path/to/labels.txt path/to/photo name_of_output.jpg

5. View your result in the output file that you named

[Click Here to view an example of this program running](https://youtu.be/SJlHo7QzScg) 
