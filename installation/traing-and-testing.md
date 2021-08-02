# Training and Testing guidline

You can train this on model your own. We used rtx1070-8GB GPU to train it for 1 day.
We provide the script here:
```bash
python main.py ddd --exp_id 3dop --dataset kitti --kitti_split 3dop --batch_size 6 --num_epochs 140 --lr 1.25e-4 --lr_step 90,120 --gpu 0 --arch hardnet_68
```


To test it
we provide raw data video to test it. please down the video with the following link.
https://drive.google.com/drive/folders/1GAfegX0IiscuW5uVByVWRnRVHHg64utt?usp=sharing
```bash
cd ./src
python test.py ddd --exp_id 3dop --dataset kitti --kitti_split 3dop --load_model /$PORJECT_ROOT/exp/ddd/3dop/model_120.pth --arch hardnet_68
```
