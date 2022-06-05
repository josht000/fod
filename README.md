# fod
Faster Object Detection

## From [Alexey Bochkovskiy | YOLOv4 and Dense Prediction Transformers](https://www.youtube.com/watch?v=nxOzeTmqe3Y)

### Fast Transformer based classifiers

* LeViT [paper](https://arxiv.org/abs/2104.01136);  [code A](https://github.com/facebookresearch/LeViT); [code  B](https://github.com/rwightman/pytorch-image-models/blob/master/timm/models/levit.py)
* https://github.com/rwightman/pytorch-image-models#models
* Self-slimmed Vision Transformer [paper](https://arxiv.org/abs/2111.12624); [code](https://github.com/Sara-Ahmed/SiT)

## From Other Notes:

* HaloNets [paper](https://arxiv.org/abs/2103.12731);  [papers with code](https://paperswithcode.com/paper/scaling-local-self-attention-for-parameter)
* CSPDarknet53 [PyTorch Code](https://rwightman.github.io/pytorch-image-models/models/csp-darknet/) 


## Strategy to enhance real time performance of object detection

**Real-time ~ 60 FPS, bs=1** 

YOLOv4 = 62 FPS on V100 (608x608 @ 43.5 AP)

1. Get baseline timings of classifier backbones: CSPDarknet53 and ResNet50 in the same framework.
2. Get timings of new classifier backbones
   1. HaloNet
   2. LeViT
   3. SiT
   4. NFNet [paper](https://arxiv.org/pdf/2102.06171.pdf)
3. Document most significant contributions from above papers
4. Identify any new data augmentation methods
5. Identify any new loss functions
6. Find or write training routine for detectors
   1. [Hugging Face]()
   2. [Ross Wightman](https://github.com/rwightman/pytorch-image-models)
   3. [theAIGuysCode](https://github.com/theAIGuysCode/tensorflow-yolov4-tflite?ref=morioh.com&utm_source=morioh.com)
7. Stich in new backbones into above, attempt to train on a dataset
8. Train baseline classifiers at 224 resolution


## Notes:
 * This article has a good break down of the yolov4 features: https://becominghuman.ai/explaining-yolov4-a-one-stage-detector-cdac0826cbd7
 * Focal loss vs cross entropy loss, vs IOU loss
 * CutMix, MixUp, mosaic, Geometric, photometric augmentation
 * Self Adversarial Training (SAT) [paper](https://arxiv.org/pdf/1911.06470.pdf)
 * Student / teacher knowledge distillation
 * CmBN (Cross mini Batch Normalization) vs Synchornized BN 
 * DropBlock Regularization
 * FCOS anchor free detector [paper](https://arxiv.org/pdf/2006.09214.pdf)