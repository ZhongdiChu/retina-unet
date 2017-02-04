#How to use this project
**Written by Yuxuan Cheng**    
<yxcheng@uw.edu>


###1. Install python.   
Use Anaconda to install python and necessary packages.
It will also install Anaconda Prompt, Spyder and Jupyter notebook. 
<https://www.continuum.io/downloads>.   

On windows, you need to download Pyhton 3.5 64bit version for installing Tensorflow (Tensorflow only support the Python 3.5 on windows)
and then you need to convert all python 2 codes of this project to python 3 version
(just using `2to3 -w ../retina-unet-master`  can convert all files in this folder automatically).   

On Mac OS X or Linux you can download Python 2.7 64bit version


###2. Install Git bash (Optional).   
Or just use the command line terminal `Win+R` then `cmd`


###3.Clone the repository from Github
Open the command line tool    
`git clone https://github.com/orobix/retina-unet`

Copy and uncompress the DRIVE into the folder
and
`mrdir drive_datasets_training_testing`

Run			
	
	python prepare_datasets_DRIVE.py

Not needed:
	
(use `print (...)` instead all `print ...` due to python 3.5)
(change to `print ()` in ./scr/retinaNN_training.py using 2to3 -w ./scr/retinaNN_training.py
2to3 -w ./src/retinaNN_training.py 
2to3 -w ./lib/extract_patches.py)

###4.Install tensorflow
Tensorflow is an open source software library for numerical computation using data flow graphs. It is powerful and easy to use on Linux or Mac.

On windows    
<https://www.tensorflow.org/get_started/os_setup#pip_installation_on_windows>
`pip install tensorflow`

install the GPU version of TensorFlow (highly recommended, if you have a compatible NAVIA graphics)

`pip install tensorflow-gpu`   
<http://www.netinstructions.com/how-to-install-and-run-gpu-enabled-tensorflow-on-windows/>

Not needed

	pip install --upgrade https://storage.googleapis.com/tensorflow/windows/gpu/tensorflow_gpu-0.12.1-cp35-cp35m-win_amd64.whl
--
####Install CUDA Toolkit 8.0
####Install cudNN
For this two part ref
<http://www.netinstructions.com/how-to-install-and-run-gpu-enabled-tensorflow-on-windows/>

--
###5.Install ConfigParser
`pip install ConfigParser`
in run_training.py change all ConfigParser to configparser (python 3.5 only)
in ./scr/retinaNN_training.py change all ConfigParser to configparser (python 3.5 only)


###6.Install Keras
`pip install keras`
and then set "image_dim_ordering": "th" in the ~/.keras/keras.json to avoid the dimension dismatch


###7.Install opecv
Windows
<http://docs.opencv.org/3.0-beta/doc/py_tutorials/py_setup/py_setup_in_windows/py_setup_in_windows.html#install-opencv-python-in-windows>

but for python 3.5 you need more work
Download the wheel from
<http://www.lfd.uci.edu/~gohlke/pythonlibs/#opencv>
`pip install opencv_python?3*win_amd64.whl`

Ref
https://www.scivision.co/install-opencv-python-windows/


Possible needed

Install h5py (for py 2.7)

------
##Possible issues:
CUDA
Failed call to cuInit: CUDA_ERROR_UNKNOWN

Could not create cud handle: CUDNN_STATUS_NOT_INITIALIZED
Update drivers?

Numpy
ImportError: cannot import name add_newdocs.   
reinstall numpy use `conda install numpy `

Keras
ImportError: No module named 'pydot'.   

	pip install pydot

AttributeError: module 'pydot' has no attribute 'find_graphviz'.   
	
	conda install pydot-ng
	conda install graphviz

and go to
`~.\Anaconda3\lib\site-packages\keras\utils\visualize_util.py `(where you installed the keras)
and comment following codes

	# if not pydot.find_graphviz():
	   # raise ImportError('Failed to import pydot. You must install pydot'
	                    # ' and graphviz for `pydotprint` to work.')


ImportError: No module named pydot

first install graphviz and then install pydot

---
Exception: "dot.exe" not found in path.
add the dot.exe to system path
D:\Program Files\Anaconda3\Library\bin\graphviz

http://www.graphviz.org/Download_windows.php   windows graphviz  
Graphviz 2.30: The msi installer is again causing problems with the PATH variable. We hope to have this fixed shortly.





