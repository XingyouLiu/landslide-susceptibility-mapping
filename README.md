# A tool for landslide susceptibility mapping(LSM) using CNN and machine learning

### Requirements
- GDAL  3.4.3
- torch 1.10.0+cu102
### Data preparation and checking
- Make sure your dataset structure same as:
```
parent
└─ origin_data
      ├── feature
	    |────xxx.tif
            |────...
            └────xxx.tif
      ├── label
	      ├── label1.tif
```
- Make sure your data's width, height, resolution, and projected coordinate system are consistent.
```
python data_check.py
```
### Training & Inference
- Training the CNN (for example with window_size=15,epochs=300)
```
python train_CNN.py --window_size 15 --epochs 300
```
- Training the ML (for example with model=ModelRF)
```
python train_ML.py --model ModelRF
```
- Generate the LSM (If out of memory, lower slide_window)
```
python generate_LSM.py --slide_window 512
```
