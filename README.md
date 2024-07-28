# fjsp-drl
Implementation of the IEEE TII paper [Flexible Job Shop Scheduling via Graph Neural Network and Deep Reinforcement Learning](https://ieeexplore.ieee.org/document/9826438). *IEEE Transactions on Industrial Informatics*, 2022.

```
@ARTICLE{9826438,  
   author={Song, Wen and Chen, Xinyang and Li, Qiqiang and Cao, Zhiguang},  
   journal={IEEE Transactions on Industrial Informatics},   
   title={Flexible Job Shop Scheduling via Graph Neural Network and Deep Reinforcement Learning},   
   year={2023},  
   volume={19},  
   number={2},  
   pages={1600-1610},  
   doi={10.1109/TII.2022.3189725}
 }
```

## Get Started

### Installation

Install using:

```shell
pip install -r requirements.txt
```

Tested with python 3.10 on macOS.

For GPU usage, please install `pynvml`. It is used in ```test.py``` to avoid excessive memory usage of GPU.

### Introduction

* ```data_dev``` and ```data_test``` are the validation sets and test sets, respectively.
* ```data``` saves the instance files generated by ```./utils/create_ins.py```
* ```env``` contains code for the DRL environment
* ```graph``` is part of the code related to the graph neural network
* ```model``` saves the model for testing
* ```results``` saves the trained models
* ```save``` is the folder where the experimental results are saved
* ```utils``` contains some helper functions
* ```config.json``` is the configuration file
* ```mlp.py``` is the MLP code (referenced from L2D)
* ```PPO_model.py``` contains the implementation of the algorithms in this article, including HGNN and PPO algorithms
* ```test.py``` for testing
* ```train.py``` for training
* ```validate.py``` is used for validation without manual calls

## Reproduce result in paper

There are various experiments in this article, which are difficult to be covered in a single run. Therefore, please change ```config.json``` before running.

Note that disabling the ```validate_gantt()``` function in ```schedule()``` can improve the efficiency of the program, which is used to check whether the solution is feasible.

### train

```
python test_running.py
```

Note that there should be a validation set of the corresponding size in ```./data_dev```.

### test

```
python test_running.py
```
Note that there should be model files (```*.pt```) in ```./model```.

## Reference

* https://github.com/zcaicaros/L2D
* https://github.com/yd-kwon/MatNet
* https://github.com/dmlc/dgl/tree/master/examples/pytorch/han

