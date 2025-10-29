# yolo_project

yolo v5 모델을 이용하여 간판이 포함된 이미지를 찍고 해당 이미지에서 간판 속 특정 단어를 인식하기



### dataset 준비

임의로 선정한 단어 '갈비'라는 키워드가 포함된 간판이 보이는 이미지 80장 선정

선정된 80장의 이미지를 roboflow를 사용해 labeling 수행 

그 후 Rotate, Crop, Roation, Brightness, Exposure, Blur 등의 증강 작업을 통해 이미지의 다양한 환경을 고려한 189장의 이미지를 만들고

165장의 train 용 이미지, 16장의 valid 용 이미지, 8장의 test 용 이미지를 포함한 dataset 준비

![Image](https://github.com/user-attachments/assets/1adbeb7c-1df3-4096-a5cf-259c66aaeb76)

### Modeling

구글 코랩을 통해 준비한 dataset을 Yolov5 모델을 이용해 학습을 진행

https://colab.research.google.com/drive/1uECnbvRNEFOkg-qme9PVQLndRCTqge0K







### result

![Image](https://github.com/user-attachments/assets/44fe50fe-a789-4252-85ac-36558bc52fd5)

16장의 검증용 이미지로 모델 검증을 수행한 결과 

Precision(정밀도) 0.819, Recall(재현율) 1.0, mAP@50 0.97, mAP@50-95 0.726을 기록함 

실제 객체를 모두 탐지하였고, 높은 예측 정확도를 보여줌

![Image](https://github.com/user-attachments/assets/6758c79f-131d-47e1-8ab0-b6d0c43109f0)

하지만 8장의 테스트용 이미지로 테스트한 결과는

잘못된 탐지가 이루어진 경우 또는 기울어져있거나 세로로 써있는 단어는 학습을 했음에도 탐지하지 못하는 결과를 보여줌



### Feedback

1. 적은 dataset 으로 인해 검증 결과와 테스트 결과에 차이가 발생, 과적합이 의심됨

    더 많고 다양한 환경의 데이터셋을 준비할 필요가 있음

2. Yolo 모델은 객체를 탐지하는 모델로, 목표로 하였던 간판 속 특정 단어를 탐지하는 것 또한

   단어를 탐지하는 것이 아닌 단어 모양을 하나의 객체로 탐지하는 것으로 선정한 주제가 Yolo 모델을 단독으로 사용하기엔 적절하지 않았음
