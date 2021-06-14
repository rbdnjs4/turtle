Install zip
and unzip

$ cd turtle_neck_openpose
$ pip3 install -r requirements.txt
Build c++ library for post processing. See : https://github.com/ildoonet/tf-pose-estimation/tree/master/tf_pose/pafprocess

$ cd tf_pose/pafprocess
$ swig -python -c++ pafprocess.i && python3 setup.py build_ext --inplace
Package Install
Alternatively, you can install this repo as a shared package using pip.

$ git clone https://www.github.com/ildoonet/tf-pose-estimation
$ cd tf-openpose
$ python setup.py install  # Or, `pip install -e .`
Models & Performances
See experiments.md

Download Tensorflow Graph File(pb file)
Before running demo, you should download graph files. You can deploy this graph on your mobile or other platforms.

cmu (trained in 656x368)
mobilenet_thin (trained in 432x368)
mobilenet_v2_large (trained in 432x368)
mobilenet_v2_small (trained in 432x368)
CMU's model graphs are too large for git, so I uploaded them on an external cloud. You should download them if you want to use cmu's original model. Download scripts are provided in the model folder.

$ cd models/graph/cmu
$ bash download.sh
Demo
Test Inference
You can test the inference feature with a single image.

$ python run_webcam2.py
