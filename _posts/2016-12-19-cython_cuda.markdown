---
layout: post
title:  "Wrap your CUDA applications in python using cython"
date:   2016-12-19 
categories: ["gpgpu"]
author: "Leiming Yu"
---

With the help of cython (a static compiler to run c/c++ code in python), you can build your own cuda applications like PyCuda.

Here is an useful example on the github, [np](https://github.com/rmcgibbo/npcuda-example).

To install cython.

```bash
$sudo apt-get update && sudo apt-get install cython
```

To record the list of installed files, you can use the following command.

```bash
$python setup.py install --record installed_files.txt
```

When you want to uninstall it, you can use xargs to do the cleaning.

```bash
$cat installed_files.txt | xargs rm -rf
```

I have committed a vector addition example in my forked [repo](https://github.com/3upperm2n/npcuda-example).

You can modify the setup.py to add more gpu architecture support.
