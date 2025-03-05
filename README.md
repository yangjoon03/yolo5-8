## 서론
* yolo 모델은 object detection모델
* [face recognition]은 object detection + CNN을 결합하여 제작하였음.
* 각 얼굴을 object로 하여 훈련

## yolo5 기본 세팅
* 모델 설치
```bush
git clone https://github.com/ultralytics/yolov5.git
```
* ✔️yolo5 모델은 cuda12 이상 버전 지원X , 호환된다고 하더라도 되지 않는다면 계속 낮춰서 해보자.
* 해결하지 않는게 정신건강에 좋다.
* 갑자기 다음날 안된다.. 정상이다. 버전을 바꿔보자!
```bush
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118                     #cuda 11.8
conda install pytorch==1.10.1 torchvision==0.11.2 torchaudio==0.10.1 cudatoolkit=11.3 -c pytorch -c conda-forge #cuda 11.3
```
* 가상환경에 설치
```bush
cd yolov5
 pip install -r requirements.txt
```

## 주피터 노트북 가상환경 연결
```bush
python -m ipykernel install --user --name 가상환경이름 --display-name "커널출력이름"
python -m ipykernel install --user --name yolo5 --display-name "yolo5"
```




## 1.모델 불러오기 2가지 방법
  * 로컬
  * pytorch hub

## 2.디렉토리 구조
```bush
📁dataset/
│── 📁images/
│   ├── 📁train/  # 훈련 이미지
│   │   ├── img_1.jpg
│   │   ├── img_2.jpg
│   │   ├── ...
│   ├── 📁val/    # 검증 이미지
│   │   ├── img_1001.jpg
│   │   ├── img_1002.jpg
│   │   ├── ...
│   ├── 📁test/   # 테스트 이미지 (선택사항)
│       ├── img_2001.jpg
│       ├── img_2002.jpg
│── 📁labels/
│   ├── 📁train/  # 훈련 데이터 라벨
│   │   ├── img_1.txt
│   │   ├── img_2.txt
│   │   ├── ...
│   ├── 📁val/    # 검증 데이터 라벨
│   │   ├── img_1001.txt
│   │   ├── img_1002.txt
│   │   ├── ...
│   ├── 📁test/   # 테스트 데이터 라벨 (선택사항)
│       ├── img_2001.txt
│       ├── img_2002.txt
│── data.yaml  # 데이터 설정 파일
```

## 3.라벨
* 텍스트 파일에는 라벨과 데이터의 이미지 좌표와 크기 정보가 들어가 있음.
*  yolo의 사전학습 된 모델을 활용하여 라벨과 바운딩박스의 정보가 들어있는 txt파일을 생성
*  txt파일을 활용하여 바운딩 박스로 표시
*  해당이미지에는 키보드,마우스 이미지가 있어 2개의 클래스의 정보가 담겨져 있다.

|클래스 ID|x_center|y_center|width	height|
|:---:|:---:|:---:|:---:|
|0|0.5|0.3|0.4|
|1|0.2|0.1|0.2|


## 4.훈련
* 주피터 노트북에서 하는 것이 아닌 bush에서 진행을 하게 된다.
* s m l x 로 훈련이 가능하다.
```bush
python "C:/Users/ailab/yolov5/train.py" --img 640 --batch 32 --epochs 100 --data "yaml 경로" --weights yolov5s.pt --device 0

```

## 5. 결과
* object detection + CNN 보다 낮은 정확도를 보임.
* 속도 측면에서는 더 빠른 결과를 나타냄.



[face recognition]: https://github.com/yangjoon03/Face_recognition
