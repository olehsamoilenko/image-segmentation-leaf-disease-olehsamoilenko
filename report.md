## My approach:
1. [DeepLabV3 model](https://pytorch.org/vision/main/models/generated/torchvision.models.segmentation.deeplabv3_resnet50.html) is used, it brings better results than [FCN](https://pytorch.org/vision/main/models/generated/torchvision.models.segmentation.fcn_resnet50.html) (both with ResNet-50 backbone)
3. Augmentations:
    - random resized crop 256x256 (most of images in dataset have this size)
    - flip, rotate
    - brightness / contrast change
    - normalize
    - resize 256x256 (for test images, brings better results)
3. [Dice loss](https://smp.readthedocs.io/en/latest/losses.html#diceloss) is ised 

## Challenges:
1. Some issues with augmentations and model input dimentions

## TODO:
1. Try with no pretrained weights:
`deeplabv3_resnet50(num_classes=1)`
2. Try [segmentation_models_pytorch](https://github.com/qubvel/segmentation_models.pytorch) models (Unet, DeepLabV3Plus etc)
