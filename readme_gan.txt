CUDA_VISIBLE_DEVICES=0 python3 src/main.py -t -metrics is fid prdc -cfg src/configs/Baby_ImageNet/BigGAN.yaml -data ./data/tiny-imagenet-200 -save outputs

batchsize: 256 
	1024 out of memory @navylap

RuntimeError: CUDA error: device-side assert triggered
	???
cifar10:

/home/ju.wang@rdte.nswc.navy.mil/Documents/PyTorch-StudioGAN/src/main.py -t -hdf5 -l -std_stat -metrics is fid prdc -ref train -cfg src/configs/CIFAR10/DCGAN.yaml -data ./data -save outputs -mpc --post_resizer friendly --eval_backbone InceptionV3_tf

ffhq:
python3 src/main.py -t -metrics is fid prdc -ref "train" -cfg src/configs/FFHQ/StyleGAN2.yaml -data ~/Documents/datasets/ffhq/ -save SAVE_PATH -mpc --pre_resizer "lanczos" --post_resizer "friendly" --eval_backbone "InceptionV3_tf"


-------- view result via wandb-------------------------
https://wandb.ai/vsurobotics/PyTorch-StudioGAN-src/runs/jbmpwrqv?nw=nwuserjwang3

https://wandb.ai/vsurobotics/PyTorch-StudioGAN-src/runs/jbmpwrqv/overview

----------------data prep ----------------------------
download scripts (link in README), mkdir data, cd data, run the wget line to download data zip, 
	run the scripts to setup data fold structure.

navylab:
	Documents/PyTorch-StudioGAN/data/

cifar10 dataset auto download when run the training script
