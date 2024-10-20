# NVS of X-Ray (CVPR25)

README.md adjusted from the original one, for more information, [click here](./README_Original.md)


## 1. Create Environment:


``` sh
# cloning our repo
git clone https://github.com/Brack-Wang/X-Gaussian.git --recursive


# install the official environment of 3DGS
cd X-Gaussian
conda env create --file environment.yml
conda activate x_gaussian

# Use our X-ray rasterizer package to replace the original RGB rasterizer
rm -rf submodules/diff-gaussian-rasterization/cuda_rasterizer
mv cuda_rasterizer submodules/diff-gaussian-rasterization/

# re-install the diff-gaussian-rasterization package
pip install submodules/diff-gaussian-rasterization
```

## 2. Data
Data locate at /data/wangfeiran/code/x/X-Gaussian/data in bajie server, copy it to the current folder




## 3. Training and Testing

You can download our trained Gaussian point clouds from [Google Drive](https://drive.google.com/drive/folders/1-JqRXiwl1zjVKuBRL3F01cWHcyAe8f2F?usp=sharing) or [Baidu Disk](https://pan.baidu.com/s/1GWE5By6u03n2l6nnFhOE0g?pwd=cyh2) (code: `cyh2`) as

We share the training log for your convienience to debug. Please download them from [Google Drive](https://drive.google.com/drive/folders/1HKcy-luYLXTSH7vviu_djVtpbSdz_v6J?usp=sharing) or [Baidu Disk](https://pan.baidu.com/s/1amk0tnpH3hN9I-Qgjb_cEQ?pwd=cyh2) (code: `cyh2`). To make the training and evaluation easier, your can directly run the `train.sh` file by

```shell
bash train.sh
```

Or you can separately train on each scene like, set --gpu_id to change GPU of training.

```shell

python3 train.py --config config/chest.yaml --eval

python3 train.py --config config/foot.yaml --eval

python3 train.py --config config/abdomen.yaml --eval

python3 train.py --config config/head.yaml --eval

python3 train.py --config config/pancreas.yaml --eval

python3 train.py --config config/jaw.yaml --eval

python3 train.py --config config/pelvis.yaml --eval

python3 train.py --config config/aneurism.yaml --eval

python3 train.py --config config/carp.yaml --eval

python3 train.py --config config/bonsai.yaml --eval

python3 train.py --config config/box.yaml --eval

python3 train.py --config config/backpack.yaml --eval

python3 train.py --config config/engine.yaml --eval

python3 train.py --config config/leg.yaml --eval

python3 train.py --config config/teapot.yaml --eval

```


## 4. Visualization

We also provide code for the visualization of rotating the Gaussian point clouds

```shell

python point_cloud_vis.py

```