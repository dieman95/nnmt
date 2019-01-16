# Neural Network Verification Model Translation Tool (NNVMT)

This repository contains an implementation of a translation tool for neural network models into the [Open Neural Network Exchange format](https://github.com/onnx) developped by Facebook and Microsoft. The tool is also able to neural network models so that the weights and biases can be exported into the Microsoft Access Table (.mat) format. We are also working on implementing printing from the ONNX format into the various input formats of the formal sverification software tools available within the research literature. 

The tool is written is Python 3. If you are using a virtual enviromnment please make sure you are using Python 3. We highly recommend the use of [Anaconda](https://www.anaconda.com/download/)

## Installing the translator
Make sure you have the following packages installed:
  - Numpy
      - ```conda install -c anaconda numpy```
  - Scipy
      - ```conda install -c anaconda scipy```
  - Keras
      - ```conda install -c anaconda keras``` 
  - ONNX
     - Instructions can be found [here](https://github.com/onnx/onnx)
  - h5py
     - ```conda install -c anaconda h5py```
  - Pathlib
     - ```conda install -c menpo pathlib``` 
### Linux
- make sure you have installed [TkInter](https://wiki.python.org/moin/TkInter)
  - if you have anaconda run:
        ```conda install -c anaconda tk```
## Parsers available for neural networks created in the following libraries:
- [Keras](https://keras.io/)
## Verification Tools Currently Supported
- [Reluplex](https://github.com/guykatzz/ReluplexCav2017)
- [Sherlock](https://github.com/souradeep-111/sherlock)
## NNMT Usage 
NNMT has been tested on MacOS Mojave Version 10.14
#### GUI 
NNMT can be run through a GUI. To use the GUI, after installing the above libraries simply run `main.py`
#### Command Line Usage
After installing the above libraries, you can run the transalator python files --help or (-h) flag to see the high-level usage:

``` 
python nnvmt.py -h

usage: nnvmt.py [-h] -i INPUT -o OUTPUT -t TOOL [-f OUTPUTFORMAT]

Neural Network Model Translation Tool

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT, --inputFile INPUT
                        path to the input file
  -o OUTPUT, --outputFile OUTPUT
                        output file path
  -t TOOL, --tool TOOL  input file type i.e (Reluplex,Keras...)
  -f OUTPUTFORMAT, --format OUTPUTFORMAT
                        output format to be translated to default: matfile
                        (.mat)
```
### Converting An Example
```python nnvmt.py -i ...nnvmt/testing/neural_network_information_13 -o ...nnvmt/examples -t Sherlock -f onnx```
#### Translating into other model formats
To convert into the formats of other tools such as [Caffe2](https://caffe2.ai/docs/getting-started.html?platform=mac&configuration=prebuilt) [PyTorch] [Matlab](https://www.mathworks.com/matlabcentral/fileexchange/67296-deep-learning-toolbox-converter-for-onnx-model-format) or [several others](http://onnx.ai/getting-started) use the ONNX converter which can be found [here](https://github.com/onnx/tutorials)

## Repository Organization
- src: contains the code for translating the models
- examples: contains several input format types that one can use to test out the tool
- testing: contains example model files from the verification tools that you can use the tool to translate. Eventually this will contain unit tests :)
- ONNX: a collection of neural network models stored in the ONNX format
## Contact
For questions please contact 
1. Patrick Musau: patrick.musau@vanderbilt.edu
2. Diego Manzanas: diego.manzanas.lopez@vanderbilt.edu


