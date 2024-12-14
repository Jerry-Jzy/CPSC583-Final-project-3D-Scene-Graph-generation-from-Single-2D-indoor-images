## 3D Scene Graph generation from Single 2D indoor images

#### code is modifed from https://github.com/AnjieCheng/SpatialRGPT.gitcd 

### Installation instruction

```sh
# Install Wis3D for visualization
pip install https://github.com/zju3dv/Wis3D/releases/download/2.0.0/wis3d-2.0.0-py3-none-any.whl

# Install detectron2 for SOM visualization
pip install 'git+https://github.com/facebookresearch/detectron2.git'

# Some other libraries
pip install iopath pyequilib==0.3.0 albumentations einops
pip install mmcv==2.0.0 -f https://download.openmmlab.com/mmcv/dist/cu116/torch1.13/index.html

#Install Grounded-SAM package and follow the instructions on the original repo: https://github.com/IDEA-Research/Grounded-Segment-Anything#install-without-docker
mkdir external && cd osdsynth/external
git clone https://github.com/IDEA-Research/Grounded-Segment-Anything.git

#Install Perspective Fields package
cd osdsynth/external
git clone https://github.com/jinlinyi/PerspectiveFields.git

#Download Weights
cd ../
sh ./scripts/download_all_weights.sh
```

### Run

```sh
python run.py --config configs/v2.py --input pictures --output-dir output --vis
```

### Visualization

```sh
wis3d --vis_dir ./output/log/Wis3D --host 0.0.0.0 --port 19090
```
