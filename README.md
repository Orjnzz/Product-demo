# Face Recognition Using MTCNN & FaceNet

## **Project Guide**


### 1. Install.
Install all the necessary libraries, use `pip` to install: 
```bash
pip install -r requirements.txt
```

---

### 2. Data Preparing.
#### Put face images of people you want to recognize in `Dataset/raw/{Name}/images.jpg...`

---

### 3. Data Preprocessing.
With the photos you have collected in `raw`, now we will cut out the face separately for training and put in the `Dataset/processed`
```bash
python src/align_dataset_mtcnn.py input_dir output_dir --image_size 'size of image' --margin 'Margin for the crop around the bounding box' --random_order --gpu_memory_fraction 'Upper bound on the amount of GPU memory'
```
Default:
```bash
python src/align_dataset_mtcnn.py Dataset/FaceData/raw Dataset/FaceData/processed --image_size 160 --margin 32 --random_order --gpu_memory_fraction 0.25
```

---

### 4. Training.
Extract features & train model by running this command:
```bash
python src/classifier.py 'mode:{TRAIN/CLASSIFY}' data_dir model --batch_size 'number of batch size'
```
Default:
```bash
python src/classifier.py TRAIN Dataset/FaceData/processed Models/20180402-114759.pb Models/facemodel.pkl --batch_size 1000
```

---

### 5. Test.
You can also use the follow this command to directly test the model:
```bash
python src/test.py
```
