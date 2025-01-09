# 安装CUDA v11.7
访问https://developer.nvidia.com/cuda-11-7-0-download-archive进行安装

# 安装并激活conda
访问https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh下载安装
conda env create -f env_cuda_latest.yaml # 可能需要使用pip降级torch以匹配CUDA版本

### Examples for **MNIST**
- MNIST
    ```
    cd ./dataset
    # python generate_MNIST.py iid - - # for iid and unbalanced scenario
    # python generate_MNIST.py iid balance - # for iid and balanced scenario
    # python generate_MNIST.py noniid - pat # for pathological noniid and unbalanced scenario
    python generate_MNIST.py noniid - dir # for practical noniid and unbalanced scenario
    # python generate_MNIST.py noniid - exdir # for Extended Dirichlet strategy 
    ```

# 运行评估
- Run evaluation: 
    ```
    cd./system
    python main.py -data MNIST -m CNN -algo FedAvg -gr 2000 -did 0
    ```
