CUDA_VISIBLE_DEVICES=0 python3 src/main.py -t -metrics is fid prdc -cfg src/configs/Baby_ImageNet/BigGAN.yaml -data ./data/tiny-imagenet-200 -save outputs

batchsize: 256 
	1024 out of memory @navylap

RuntimeError: CUDA error: device-side assert triggered
	???
cifar10:

/home/ju.wang@rdte.nswc.navy.mil/Documents/PyTorch-StudioGAN/src/main.py -t -hdf5 -l -std_stat -metrics is fid prdc -ref train -cfg src/configs/CIFAR10/DCGAN.yaml -data ./data -save outputs -mpc --post_resizer friendly --eval_backbone InceptionV3_tf

ffhq:
CUDA_VISIBLE_DEVICES=0
python3 src/main.py -t -metrics is fid prdc -ref "train" -cfg src/configs/FFHQ/StyleGAN2.yaml -data ~/Documents/datasets/ffhq/ -save SAVE_PATH -mpc --pre_resizer "lanczos" --post_resizer "friendly" --eval_backbone "InceptionV3_tf"
	ffhq download 89gb zipfile, unzip, move to train/
	datavision/ffhq
	run time error due to nvcc compiling error
	try docker (sudo)
	docker pull alex4727/experiment:pytorch113_cuda116

unsorted:
  221  sudo docker pull alex4727/experiment:pytorch113_cuda116
  222  docker run -it --gpus all --shm-size 128g --name StudioGAN -v /tmp/test/PyTorch-StudioGAN:/root/code -v /data:/data --workdir /root/code alex4727/experiment:pytorch113_cuda116 /bin/zsh
  223  sudo docker run -it --gpus all --shm-size 128g --name StudioGAN -v /tmp/test/PyTorch-StudioGAN:/root/code -v /data:/data --workdir /root/code alex4727/experiment:pytorch113_cuda116 /bin/zsh
  224  history
sudo docker run -it --gpus all --shm-size 128g --name StudioGAN -v /tmp/test/PyTorch-StudioGAN:/root/code -v /data:/data --workdir /root/code maximedurand/stylegan3:latest bash	

pip install -r requiremetns.txt
pip install --upgrade pydantic
	for typing_extentions error
ln -sn /data/systest/ffhq/
wandb api key:
	a180e9149e0635d81154fc02517643e8a8beea1d


 Setting up PyTorch plugin "bias_act_plugin"... Failed!
	ffhq run fail. old torch version vs a100 chip?

-------- view result via wandb-------------------------
https://wandb.ai/vsurobotics/PyTorch-StudioGAN-src/runs/jbmpwrqv?nw=nwuserjwang3

https://wandb.ai/vsurobotics/PyTorch-StudioGAN-src/runs/jbmpwrqv/overview

----------------data prep ----------------------------
download scripts (link in README), mkdir data, cd data, run the wget line to download data zip, 
	run the scripts to setup data fold structure.

navylab:
	Documents/PyTorch-StudioGAN/data/

cifar10 dataset auto download when run the training script
