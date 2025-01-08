# 3D Gaussian Splatting

### 프로젝트 개요

이 프로젝트는 **3D Gaussian Splatting(3DGS)** 기술을 활용하여 **멀티뷰 이미지 데이터**로부터 3D 장면을 렌더링하고 평가합니다. 제공된 스크립트를 통해 데이터 학습, 렌더링, 품질 평가(PSNR 및 SSIM)를 자동으로 수행합니다. 주요 특징은 다음과 같습니다:

**효율적 학습**: Gaussian Splatting을 이용해 멀티뷰 데이터를 학습.

**3D 렌더링**: 학습된 모델을 사용해 새로운 시점의 3D 장면을 렌더링.

**평가 지표**: PSNR 및 SSIM을 계산하여 렌더링 품질 평가.



### 주요 기능

1. **3D Gaussian Splatting**: 멀티뷰 이미지 데이터를 기반으로 3D 장면 구조와 시각적 정보를 효율적으로 학습 및 표현.
2. **품질 평가**: Ground Truth와 렌더링된 이미지를 비교하여 PSNR 및 SSIM 지표 계산.
3. **비디오 출력**: 렌더링 결과와 Ground Truth 이미지를 비디오로 변환해 결과 시각화.




## 설치 방법

**1. **환경 준비****
Google Colab 또는 CUDA가 지원되는 로컬 환경
**2. 설치 과정**


1. 프로젝트 클론:

```
git clone --recursive https://github.com/camenduru/gaussian-splatting
cd gaussian-splatting
   ```


2. 필요한 패키지 설치:
```
pip install plyfile
pip install ./submodules/diff-gaussian-rasterization
pip install ./submodules/simple-knn
```


3. 데이터 다운로드 및 압축 해제
```
wget https://huggingface.co/camenduru/gaussian-splatting/resolve/main/tandt_db.zip
unzip tandt_db.zip
```

# 사용 방법


**1. 학습**
```
python train.py -s /content/gaussian-splatting/tandt/train
```


**2. 렌더링**
```
python render.py -m /content/gaussian-splatting/GaussianViewTest/model
```


**3. 결과 생성**
```
ffmpeg -framerate 3 -i /content/gaussian-splatting/GaussianViewTest/model/train/ours_30000/renders/%05d.png -c:v libx264 -r 3 -pix_fmt yuv420p renders.mp4
ffmpeg -framerate 3 -i /content/gaussian-splatting/GaussianViewTest/model/train/ours_30000/gt/%05d.png -c:v libx264 -r 3 -pix_fmt yuv420p gt.mp4
```

# 평가 방법

### PSNR 및 SSIM 계산
skimage.metrics 라이브러리를 사용해 Ground Truth와 렌더링된 이미지의 품질을 평가합니다:

1. PSNR(신호 대 잡음비): 픽셀 간 차이를 측정하여 품질 평가.
2. SSIM(구조적 유사도 지수): 이미지의 구조적 유사성을 평가.


평균 PSNR 및 SSIM 값을 출력:
```
python calculate_metrics.py
```


## 결과
렌더링된 비디오(renders.mp4): 학습된 모델이 생성한 새로운 시점의 장면.
Ground Truth 비디오(gt.mp4): 실제 Ground Truth 데이터를 기반으로 한 비디오.

평가 지표:
평균 PSNR: xx.x dB
평균 SSIM: 0.xxxx

## 3DGS
![renders+(1)+(1)](https://github.com/user-attachments/assets/49d8f136-a474-4b84-b1b5-435f3767a9e3)
#renders
![gt+(1)+(1) (1)](https://github.com/user-attachments/assets/986db1e4-2d99-4057-9a62-e427dbc433cf)
#gt


## 참조 자료
관련 연구: 3D Gaussian Splatting for Real-Time Rendering

github : 

https://github.com/graphdeco-inria/gaussian-splatting

https://github.com/camenduru/gaussian-splatting-colab
