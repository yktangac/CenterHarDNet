# Installation
working envrionment:
```bash
Os: Ubuntu20.04 (Windows10 not yet tested)
Cuda: 10.2
pytorch: 1.2.0 (we can't use the original pytorch version 0.4.0)
conda envrionment(recommended)
```

# Original. (Follow the original repo):
There are many issues with the original repo. https://github.com/xingyizhou/CenterNet/blob/master/readme/INSTALL.md#installation

# What I added. (We upload our fixed)
What you need to do is to install the cocoAPI with following the link above.
You need to link the cocoAPI in your conda environment.
You can compile the DCNv2 but not needed in hardnet to verify whether everything is set up.
download the hardNet68 pre-trained models with this URL: https://drive.google.com/file/d/1Szcpo9J2j8ViWVEJeUQwrQjhWM6sQNeN/view?usp=sharing 
move the ```hardnet68_base.pth``` into src directory

compile the DCNv2 but not needed in hardnet to verify whether everything is set up.
also compile the NMS in ```./src/lib/external``` by ```make``` for testing


Run the demo to see all setup is done or not.
To run the demo, we provide our pre-trained model. Download it.
https://drive.google.com/file/d/1yhvlUOhnU4LICx2AJeJDPxV54DjkBd5e/view?usp=sharing

# Quick Demo:
we provide raw data video to test it. please down the video with the following link.
https://drive.google.com/drive/folders/1GAfegX0IiscuW5uVByVWRnRVHHg64utt?usp=sharing
```bash
cd $WORKPLACE_ROOT/src
python demo.py ddd --demo /path/to/image/or/folder/or/video --load_model /path/you/save/to/hardnetddd.pth --arch hardnet_68 --debug 2
```

