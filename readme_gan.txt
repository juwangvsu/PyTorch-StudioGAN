CUDA_VISIBLE_DEVICES=0 python3 src/main.py -t -metrics is fid prdc -cfg src/configs/Baby_ImageNet/BigGAN.yaml -data ./data/tiny-imagenet-200 -save outputs

batchsize: 256 
	1024 out of memory @navylap

RuntimeError: CUDA error: device-side assert triggered
	???

-------- view result via wandb-------------------------
https://wandb.ai/vsurobotics/PyTorch-StudioGAN-src/runs/jbmpwrqv?nw=nwuserjwang3

----------------data prep ----------------------------
download scripts (link in README), mkdir data, cd data, run the wget line to download data zip, 
	run the scripts to setup data fold structure.

navylab:
	Documents/PyTorch-StudioGAN/data/

cifar10 dataset auto download when run the training script
