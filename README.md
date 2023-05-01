# Barcode_Identifier_YoloV3

_______
_A Collage of Training images_
<img src="https://raw.githubusercontent.com/shilpiprd/Barcode_Identifier_YoloV3/master/output/recognized_.jpeg" alt="Image" width="600" height="400">
YoloV3 Simplified for training on Colab with custom dataset. 
The aim of this repository is to be able to identify barcodes from images using YoloV3 model.
The YOLOv3 model for barcode detection  enables automated identification of barcodes in real-time.By using deep learning algorithms, the model can detect barcodes from various angles and orientations, making the process faster and more accurate than traditional methods. This can lead to significant time and cost savings

I have used 826 images as training_set out of which some contain the barcode and some dont. 
The corresponding label file (.txt file) of images which don't contain the object is empty. 
For test, I've used 208 images of the same order as above. 
The training and test images have been resized to the standard input size of YoloV3 by using Pillow. 


You'll need to download the weights from the original source. 
To be able to run the colab notebook, follow the given steps:
1. Create a folder called weights in the root folder.
2. Download from: https://drive.google.com/file/d/1vRDkpAiNdqHORTUImkrpD7kK_DkCcMus/view?usp=share_link
3. Place 'yolov3-spp-ultralytics.pt' file in the weights folder:
  * to save time, move the file from the above link to your GDrive
  * then drag and drop from your GDrive opened in Colab to weights folder
4. run this command
!python train.py --data data/customdata/custom.data --batch 10 --cache --cfg cfg/yolov3-custom.cfg --epochs 300 --nosave

The hierarchy of the data file is as follows:
```
data
  --customdata
    --train_images/
      --img001.png
      --img002.png
      --...
    --test_images/
      --_img001.png
      --_img002.png
      --...
    --train_labels/
      --img001.txt
      --img002.txt
      --...
    --test_labels/
      --_img001.txt 
      --_img002.txt
      --...
    custom.data #data file
    custom.names #contains the class name (barcode)
    custom_train.txt #list of name of the training images that our model will be trained on. 
    custom_test.txt #list of names of the test images that our model will be tested on.
```

We get good results: 
<img src="https://raw.githubusercontent.com/shilpiprd/Barcode_Identifier_YoloV3/master/output/320201211_4178_rgb.png" alt="Image" width="400" height="300">





