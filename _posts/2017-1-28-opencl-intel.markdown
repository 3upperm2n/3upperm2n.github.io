---
layout: post
title:  "Install Intel OpenCL on ubuntu 16.04"
date:   2017-1-28
categories: ["parallel"]
author: "Leiming Yu"
---


### Download intel_sdk_for_ocl_applications_2014_ubuntu_5.0.0.43_x64 from intel 
```bash
$wget -c http://registrationcenter.intel.com/irc_nas/5193/intel_code_builder_for_opencl_2015_ubuntu_5.0.0.43_x64.tgz
```

### install dependency
```bash
sudo add-apt-repository "deb http://security.ubuntu.com/ubuntu trusty-security main”
sudo apt-get update
sudo apt-get install lsb-core libicu52
```

### install sdk
```bash
$tar -xvzf intel_code_builder_for_opencl_2015_ubuntu_5.0.0.43_x64.tgz
$cd intel_sdk_for_ocl_applications_2014_ubuntu_5.0.0.43_x64/
$sudo ./install_GUI.sh
```

Now, the sdk is installed in /opt/intel/intel-opencl-1.2-5.0.0.43/

### edit ~/.bashrc
```bash
export PATH=$PATH:/opt/intel/intel-opencl-1.2-5.0.0.43/opencl-sdk/include       
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/opt/intel/intel-opencl-1.2-5.0.0.43/opencl-sdk/lib64
```


### create conf for intel opencl
```bash
$echo "/opt/intel/intel-opencl-1.2-5.0.0.43/opencl-sdk/lib64" | sudo tee -a /etc/ld.so.conf.d/intelOpenCL.conf > /dev/null
```

### icd for intel opencl 
```bash
$sudo ln -s /opt/intel/opencl-1.2-5.0.0.43/etc/intel64.icd /etc/OpenCL/vendors/intel64.icd
$sudo ldconfig
```

### check installation
If clinfo is not installed, use the following command.
```bash
$sudo apt-get install clinfo
$clinfo | grep Intel
```
