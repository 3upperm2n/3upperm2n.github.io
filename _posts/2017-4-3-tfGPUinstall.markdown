---
layout: post
title:  "Install tensorflow (gpu supported version) in ubuntu 16.04"
date:   2017-4-3
categories: ["gpgpu"]
author: "Leiming Yu"
---
If install tf using conda, the default version currently is 1.0.0 with no gpu support. 
```
conda install -c conda-forge tensorflow
```

In order to have a gpu-supported tf, use pip to install.
```
pip install tensorflow-gpu
```

You can verify the setup using the following script.
```python
from distutils.version import LooseVersion
import warnings
import tensorflow as tf

# Check TensorFlow Version
assert LooseVersion(tf.__version__) >= LooseVersion('1.0'), 'Please use TensorFlow version 1.0 or newer'
print('TensorFlow Version: {}'.format(tf.__version__))

# Check for a GPU
if not tf.test.gpu_device_name():
	warnings.warn('No GPU found.')
else:
	print('Current GPU Device: {}'.format(tf.test.gpu_device_name()))
```

### Reference
* https://www.tensorflow.org/versions/r0.12/get_started/os_setup 
