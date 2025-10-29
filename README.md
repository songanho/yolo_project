# yolo_project

yolo v5 모델을 이용하여 간판에 포함된 이미지를 찍고 해당 이미지에서 간판 속 특정 단어를 인식하기

### dataset 준비

임의로 선정한 단어 '갈비'라는 키워드가 포함된 간판이 보이는 이미지 80장 선정

선정된 80장의 이미지를 roboflow를 사용해 labeling 수행 

그 후 Rotate, Crop, Roation, Brightness, Exposure, Blur 등의 증강 기을 사용해 이미지의 다양한 환경을 고려 총 189장의 이미지를 만들고

165장의 train 용 이미지, 16장의 valid 용 이미지, 8장의 test 용 이미지를 포함한 dataset 준비

![Image](https://github.com/user-attachments/assets/1adbeb7c-1df3-4096-a5cf-259c66aaeb76)

### Modeling

구글 코랩을 통해 준비한 dataset을 Yolov5 모델을 이용해 학습을 진행

https://colab.research.google.com/drive/1uECnbvRNEFOkg-qme9PVQLndRCTqge0K







### result

![Image](https://github.com/user-attachments/assets/44fe50fe-a789-4252-85ac-36558bc52fd5)

![Image](https://github.com/user-attachments/assets/6758c79f-131d-47e1-8ab0-b6d0c43109f0)
