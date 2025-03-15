# Material Classification using tensorflow keras

## 모델 설명

1. **데이터 로딩**
   - cardboard, glass, metal, paper, plastic, trash의 6개 클래스를 각각의 디렉토리에 저장합니다.
   - `flow_from_director()`를 사용하여 디렉토리의 구조를 기반으로 데이터를 불러오고, 이를 `ImageDataGenerator`와 함께 학습에 적합한 형태로 변환합니다.
2. **신경망 구조 및 학습 과정**
   - 컨볼루션 레이어:
     - `Conv2D`를 이용하여 이미지의 특징을 추출합니다.
     - 활성화 함수로 `ReLU`를 사용합니다.
   - 풀링 레이어:
     - `MaxPooling2D`를 하용하여 중요한 특징을 유지하면서 계산량을 감소시킵니다.
   - 완전 연결 레이어:
     - `Flatten()`을 사용하여 다차원 특성 맵을 1차원 벡터로 변한환 후, `Dense` 레이어에 전달합니다.
   - 출력 레이어:
     - `softmax` 활성화 함수를 사용하여 6개의 클래스로 다중 분류를 수행합니다.
     - 각 클래스에 대한 확률값을 출력하여, 가장 높은 확률을 가진 클래스가 예측값이 됩니다.

## 패키지 구조

```
📂 sample_data       # 데이터셋 폴더 (다중 클래스 이미지 분류를 위한 이미지 데이터 저장)
    ├──📂 cardboard  # 'cardboard' 클래스 이미지 저장 (골판지 이미지)
    ├──📂 glass      # 'glass' 클래스 이미지 저장 (유리 이미지)
    ├──📂 metal      # 'metal' 클래스 이미지 저장 (금속 이미지)
    ├──📂 paper      # 'paper' 클래스 이미지 저장 (종이 이미지)
    ├──📂 plastic    # 'plastic' 클래스 이미지 저장 (플라스틱 이미지)
    └──📂 trash      # 'trash' 클래스 이미지 저장 (기타 쓰레기 이미지)
📄 material.ipynb    # Jupyter Notebook 파일 (데이터 분석, 모델 학습, 시각화 등의 작업 수행)
📄 README.md         # 프로젝트 설명 파일 (데이터셋 구조, 모델 설명 등 포함)
```
