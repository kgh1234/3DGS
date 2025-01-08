GS-IR: 3D Gaussian Splatting for Inverse Rendering
프로젝트 개요
GS-IR은 3D Gaussian Splatting(3DGS) 기술을 기반으로 역 렌더링 문제를 해결하는 최신 기술입니다. 이 프로젝트는 주어진 멀티뷰 이미지 데이터를 활용하여 **장면의 물리적 속성(기하학, 재질, 조명)**을 복원하고, 이를 통해 다음과 같은 작업을 수행합니다:

재조명(Relighting): 새로운 조명 조건에서 장면을 다시 렌더링.
재질 편집(Material Editing): 표면의 재질 속성을 조정.
새로운 시점 합성(Novel View Synthesis): 새로운 카메라 위치에서 장면 생성.
이 프로젝트는 다음을 포함합니다:

멀티뷰 학습 데이터 처리
3D Gaussian 기반 장면 복원
PSNR 및 SSIM을 통한 품질 평가
Ground Truth와 비교하여 출력 영상 생성

# 3DGS
![renders+(1)+(1)](https://github.com/user-attachments/assets/49d8f136-a474-4b84-b1b5-435f3767a9e3)
#renders
![gt+(1)+(1) (1)](https://github.com/user-attachments/assets/986db1e4-2d99-4057-9a62-e427dbc433cf)
#gt
