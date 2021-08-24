# Building-Footprint-Extraction-Practical-Project
Practical Project for Semantic Segmentation of Building Footprint from Satellite Images

## Dataset Exploration
- Toby's dataset
- other's dataset

## Annotate (1 day)
- labelme

## preprocess (2 day)
Annotation
- labelme --> coco json
- coco --> binary mask np array --> png format save
- format ready to feed into model

Image
- read geotiff with tifffile --> np array
- visualize, resize(scale)
- pad, crop = 10000,10000 --> 256/512/324 tiles
- save png format

## Data Pipeline
- train (3 day)
	- model = UNet, Deep UNet
	- loss = Dice Focal
	- optimizer = Adam
	- metrics = ?

## Inference pipeline / post process (3 day)
- ?
toby

## To Do
- [ ] models.py (UNet, DeepUNet)
- [ ] dataset.py
- [ ] loss.py
- [x] ANT - clean & refactor generate images function
- [ ] ANT - add save weight code in Train.ipynb
- [x] ANT - change directories of output files (create dataset, train, inference)
- [ ] Toby - georeference script() = georefernce(png = False, shape_file = True, tiff = True, point_file = True)

### Output folder structure
	outputs/
	     - dataset/
	        - images/
	        - mask/		
	     - model weights/ --> my_model.h5
	     - inference outputs/
	        - png/ --> binary_mask.png
	        - shp/ --> shape files
	        - tiff/ --> mask.tiff

### Output folder directories
```
# dataset creation
outputs/dataset/
outputs/dataset/images/
outputs/dataset/masks/

# save model weights in this folder
outputs/model weights/

# save inference output files in separate folders
outputs/inference outputs/
outputs/inference outputs/png/
outputs/inference outputs/shp/
outputs/inference outputs/tiff/
```
