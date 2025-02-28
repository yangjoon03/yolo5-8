## yolo5 기본 세팅
* 모델 설치
```bush
git clone https://github.com/ultralytics/yolov5.git
```
*✔️yolo5 모델은 cuda12 이상 버전 지원X , 호환된다고 하더라도 되지 않는다면 계속 낮춰서 해보자.
* 정신건강에 좋다.
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

## 2.yaml 파일 만들기

## 3.


## 4.훈련
* 주피터 노트북에서 하는 것이 아닌 bush에서 진행을 하게 된다.
