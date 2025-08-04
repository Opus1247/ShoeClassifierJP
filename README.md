# ShoeClassifier
My name is James Palmer Walker and for my project, I made a shoe classifier with the Jetson Orin Nano. The ShoeClassifier AI uses the re-trained resnet18 model to classify popular sneakers. 

# Algorithm
Based on the [Popular Sneakers Classification dataset]([url](https://www.kaggle.com/datasets/nikolasgegenava/sneakers-classification)) it classifies images of sneakers using resnet18. 

# Requirements 
1. Jetson Orin Nano
2. Model - https://drive.google.com/file/d/1nC--usNy-QVmqExRd2DRLsylwgN_BNiT/view?usp=sharing save to: models/sneakers-dataset/resnet18.onnx
3. Dataset - https://www.kaggle.com/datasets/nikolasgegenava/sneakers-classification
4. NET=models/sneakers_dataset DATASET=data/sneakers_dataset 5. Internet connection

# Steps 
1. SSH into Jetson: ssh username@<jetson-ip-address>
2. Clone the repository: git clone https://Opus1247/ShoeClassifierJP.git cd sneakers-dataset
3. Install requirements: pip3 install -r requirements.txt
4. Project structure
.
├── models/
│   └── sneakers-dataset/
│       ├── resnet18.onnx           ← exported ONNX model
│       ├── labels.txt              ← class labels
│       └── test/ │           └── 002.jpg             ← test image
├── onnx_export.py
├── README.md
5. Optional - python3 onnx_export.py --model-dir=models/sneakers-dataset
6. Run with imagenet: imagenet.py \ --model=models/sneakers-dataset/resnet18.onnx \ --input_blob=input_0 \ --output_blob=output_0 \ --labels=models/sneakers-dataset/labels.txt \ models/sneakers-dataset/test/002.jpg Or just use the source files
