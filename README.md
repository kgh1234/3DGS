#GS-IR: 3D Gaussian Splatting for Inverse Rendering
프로젝트 개요
이 프로젝트는 3D Gaussian Splatting(3DGS) 기술을 활용하여 멀티뷰 이미지 데이터로부터 3D 장면을 렌더링하고 평가합니다. 제공된 스크립트를 통해 데이터 학습, 렌더링, 품질 평가(PSNR 및 SSIM)를 자동으로 수행합니다. 주요 특징은 다음과 같습니다:

- 효율적 학습: Gaussian Splatting을 이용해 멀티뷰 데이터를 학습.
- 3D 렌더링: 학습된 모델을 사용해 새로운 시점의 3D 장면을 렌더링.
- 평가 지표: PSNR 및 SSIM을 계산하여 렌더링 품질 평가.

**주요 기능**
1. 3D Gaussian Splatting: 멀티뷰 이미지 데이터를 기반으로 3D 장면 구조와 시각적 정보를 효율적으로 학습 및 표현.
2. 품질 평가: Ground Truth와 렌더링된 이미지를 비교하여 PSNR 및 SSIM 지표 계산.
3. 비디오 출력: 렌더링 결과와 Ground Truth 이미지를 비디오로 변환해 결과 시각화.


**설치 방법**
1. 환경 준비
Google Colab 또는 CUDA가 지원되는 로컬 환경
2. 설치 과정
프로젝트 클론:
git clone --recursive https://github.com/camenduru/gaussian-splatting
cd gaussian-splatting
   




# 3DGS
![renders+(1)+(1)](https://github.com/user-attachments/assets/49d8f136-a474-4b84-b1b5-435f3767a9e3)
#renders
![gt+(1)+(1) (1)](https://github.com/user-attachments/assets/986db1e4-2d99-4057-9a62-e427dbc433cf)
#gt
