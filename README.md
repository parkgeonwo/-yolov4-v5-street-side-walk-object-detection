# yolov4,v5-street-side-walk-object-detection
yolo v4, v5를 활용한 도보 위 객체 탐지 모델 개발

### 1. 개발 환경

- python
- R
- tensorflow
- pytorch
- colab

### 2. 개발 기획

2-1) 도로 위, 킥보드의 무분별한 주차 문제 심화

위치를 가리지 않고 불법 주정차 된 킥보드로 인해 많은 보행자들은 보행 안전에 위협을 받고 있다. 이에 서울시에서는 2021년 07월 15일 이후 불법 주차 단속을 강력하게 진행하고 있지만, 곳곳에 만연한 불법주차를 단속하고 체계를 잡기 까지는 많은 시간이 걸릴 것으로 예상된다. 
  
2-2) 시각장애인들에게 기존의 도보 위 장애물 문제와 결합

일반 보행자에게도 큰 보행위협을 가져다주는 불법주차 문제는 시각장애인에게는 더욱 큰 위협이다. 특히 킥보드는 그 생김새로 인해 대체적으로 예상할 수 없게 주차되어 있는 경우가 많다. 

그러나 킥보드라는 최근 이슈로 인해 시각장애인들의 보행 안전 문제가 붉어졌을 뿐이지 시각장애인 분들께서 기존에 존재했던 보도 문제는 충분히 존재했다. 

### 3. 진행과정

주제 선정 및 데이터 수집 --> XML 형식 라벨링 데이터 변환 작업 --> 추가 이미지 수집 및 라벨링

--> 모델 설계 및 학습 --> 모델을 Tensorflow lite로 변형하여 안드로이드 휴대폰에서 실행


### 4. 모델 적용 데이터

4-1) AI HUB의 “인도 보행 영상” 데이터 중 Bounding box 352,810장 중 1900장

<img width="50%" src="https://user-images.githubusercontent.com/87109907/144701690-881c13d4-75f3-45d5-a30c-2a35ebc240f5.png"/>


4-2) 구글, 다음, 빙, 네이버에서 직접 크롤링하고, 라벨링한 킥보드 데이터 300장

<img width="30%" src="https://user-images.githubusercontent.com/87109907/144701699-fa0c5a96-9ea5-4973-b694-7bdd3eb1ff88.png"/>  <img width="30%" src="https://user-images.githubusercontent.com/87109907/144701702-1da6f0b1-0005-4818-9758-d45be72ac3a7.png"/>


### 5. 적용 기술

실시간 객체 탐지 모델인 YOLO(You Look Only Once) 모델을 사용하여 외부기기에 적용할것이다.

기존의 R-CNN 모델은 이미지를 여러장으로 분할 후 CNN 모델을 이용해 이미지를 
분석했지만, YOLO 모델은 이미지 전체를 한번만 보는 특징이 있다.

또한, Faster R-CNN 모델(0.5FPS)보다 FPS가 월등히 빨라(45FPS) 돌발적인 상황에 가장 
어울리는 모델이다.

### 6. 분석 결과

<img width="50%" src="https://user-images.githubusercontent.com/87109907/144701782-00b65a40-9961-40b0-a24d-0bea966d8ea0.PNG"/>

### 7. 결과 이미지 


<img width="45%" src="https://user-images.githubusercontent.com/87109907/144701800-ce81cecb-bbfc-4bdf-8e37-b728ed9dccee.png"/>

<img width="45%" src="https://user-images.githubusercontent.com/87109907/144701802-40faed93-8b1a-4db3-ab4a-7dc6558b5e17.png"/>















