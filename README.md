# Installation
```
mamba create -n wm3dp python=3.10
mamba activate wm3dp
pip3 install --pre torch torchvision torchaudio --index-url https://download.pytorch.org/whl/nightly/cu126
mamba install ffmpeg
pip3 install decord einops evo transformers diffusers tqdm timm notebook dreamsim torcheval lpips ipywidgets
```

# Training
```
export SLURM_NTASKS=1
python train.py --config config/test_cdit_xl.yaml --ckpt-every 2000 --eval-every 10000 --bfloat16 1 --epochs 300  --torch-compile 0
```
