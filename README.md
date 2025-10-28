# yolo_project

yolo v5 모델을 이용하여 간판에 포함된 이미지를 찍고 해당 이미지에서 간판 속 특정 단어를 인식하기

### dataset 준비

임의로 선정한 단어 '갈비'라는 키워드가 포함된 간판이 보이는 이미지 80장 선정

선정된 80장의 이미지를 roboflow를 사용해 labeling 수행 

그 후 Rotate, Crop, Roation, Brightness, Exposure, Blur 기능을 사용해 한 이미지를 다양한 이미지로 만들어 총 189장의 이미지를 포함한 데이터셋 생성
