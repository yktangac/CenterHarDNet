# How to put kitti dataset in this repo

initial directory structure:
```bash
${CenterNet_ROOT}
|-- data
`-- |-- kitti
    `-- |-- training
        |   |-- image_2
        |   |-- label_2
        |   |-- calib
        |-- ImageSets_3dop
        |   |-- test.txt
        |   |-- train.txt
        |   |-- val.txt
        |   |-- trainval.txt
        `-- ImageSets_subcnn
            |-- test.txt
            |-- train.txt
            |-- val.txt
            |-- trainval.txt

```
final directory structure:
```bash
.
└── kitti
    ├── annotations
    ├── images
    │   └── trainval -> /home/uav/project/CtNmbv3/data/kitti/training/image_2
    ├── ImageSets_3dop
    ├── ImageSets_subcnn
    └── training
        ├── calib
        ├── image_2
        └── label_2

```


1. creating kitti under data directory
```bash
cd /path/to/your/workspace/data
mkdir kitti
```
2. Prepare Kitti datasets:
You may download the kitti dataset via the following links:
KITTI image dataset:
Download: data_object_calib.zip
https://s3.eu-central-1.amazonaws.com/avg-kitti/data_object_calib.zip 

Download: data_object_calib.zip
https://s3.eu-central-1.amazonaws.com/avg-kitti/data_object_det_2.zip

Download: data_object_image_3.zip
https://s3.eu-central-1.amazonaws.com/avg-kitti/data_object_image_3.zip

Download: data_object_image_2.zip
https://s3.eu-central-1.amazonaws.com/avg-kitti/data_object_image_2.zip

Download: data_object_label_2.zip
https://s3.eu-central-1.amazonaws.com/avg-kitti/data_object_label_2.zip

ImageSets_3dop and ImageSets_subcnn will be uploaded in the main directory in this repo.
Please move those to kitti directory for generating annotation json files.

3. convert kitti format to coco format:
create annotations directory under kitti first. The original repo from Zhou doesn't have it
```bash

mkdir annotations
```
prepare the kitti dataset as the above intial structure.
then run the ```bash convert_kitti_to_coco.py``` to generate kitti annotations:
```bash
cd ./src/lib/tools
python convert_kitti_to_coco.py
```

4. create images directory and link image folder:
```bash
cd ${CenterNet_ROOT}/data/kitti/
mkdir images
ln -s training/image_2 images/trainval
```
5. then use tree -d to check whether the structure looks like
```
bash
.
└── kitti
    ├── annotations
    ├── images
    │   └── trainval -> /home/uav/project/CtNmbv3/data/kitti/training/image_2
    ├── ImageSets_3dop
    ├── ImageSets_subcnn
    └── training
        ├── calib
        ├── image_2
        └── label_2

```


