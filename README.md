# Face Recognition Using MTCNN & FaceNet

## **Project Guide**

---

### 1. Install.
Install all the necessary libraries, use `pip` to install: 
```bash
pip install -r requirements.txt
```

---
### 2. Prepare data.
Put images of people you want to recognize in `Dataset/raw/{Name}/images.jpg...`
---

### 3. Data Preprocessing.
With the photos you have collected in `raw`, now we will cut out the face separately for training and put in the `Dataset/processed`
```bash
python input_dir output_dir --image_size 'size of image' --margin 'Margin for the crop around the bounding box' --random_order --gpu_memory_fraction 'Upper bound on the amount of GPU memory'
```
Default:
```bash
python src/align_dataset_mtcnn.py Dataset/FaceData/raw Dataset/FaceData/processed --image_size 160 --margin 32 --random_order --gpu_memory_fraction 0.25
```


