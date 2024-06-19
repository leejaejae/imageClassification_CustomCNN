
# README

## 사자와 호랑이 이미지 분류를 위한 커스텀 CNN (Google Colab에서 실행)

이 프로젝트는 PyTorch를 사용하여 커스텀 합성곱 신경망(CNN)을 구축하고, 이를 통해 사자와 호랑이 이미지를 분류하는 작업을 다룹니다. 전체 구현은 Google Colab에서 실행됩니다.

### 목차
1. [프로젝트 개요](#프로젝트-개요)
2. [설치](#설치)
3. [데이터셋 준비](#데이터셋-준비)
4. [모델 훈련](#모델-훈련)
5. [모델 평가](#모델-평가)
6. [결과 시각화](#결과-시각화)

### 프로젝트 개요
이 프로젝트의 목표는 사자와 호랑이 이미지를 자동으로 분류할 수 있는 딥러닝 모델을 개발하는 것입니다. 이를 위해 커스텀 CNN을 사용하며, 모델의 훈련과 검증, 테스트는 각각 70%, 15%, 15%의 데이터로 수행됩니다.

### 설치
프로젝트를 실행하기 위해서는 다음과 같은 라이브러리가 필요합니다:
- PyTorch
- torchvision
- PIL (Python Imaging Library)
- numpy
- matplotlib

Google Colab을 사용하면 별도의 설치 과정 없이 이 모든 라이브러리를 사용할 수 있습니다.

### 데이터셋 준비
이미지 데이터셋은 `/mnt/lion`와 `/mnt/tiger` 디렉토리에 각각 사자와 호랑이 이미지를 저장합니다. 데이터셋은 다음과 같은 디렉토리 구조를 가집니다:
```
/mnt
  ├── lion
  │   └── lion1.jpg
  │   └── lion2.jpg
  │   └── ...
  ├── tiger
  │   └── tiger1.jpg
  │   └── tiger2.jpg
  │   └── ...
```
이미지 경로와 라벨을 지정하고 데이터셋을 로드한 후, 훈련, 검증, 테스트 데이터셋으로 분할합니다.

### 모델 훈련
모델 훈련은 커스텀 CNN을 사용하여 수행됩니다. 모델은 여러 층의 합성곱 계층과 완전 연결 계층으로 구성되어 있습니다. 최적화는 Adam 옵티마이저를 사용하며, 교차 엔트로피 손실을 최소화하는 방향으로 훈련합니다. 훈련 도중 검증 데이터셋을 이용하여 모델 성능을 평가하고, 최적의 모델을 저장합니다.

### 모델 평가
저장된 최적의 모델을 로드하여 테스트 데이터셋에 대해 평가를 수행합니다. 모델의 최종 정확도를 출력합니다.

### 결과 시각화
훈련 및 검증 과정에서의 손실과 정확도를 시각화하여 모델의 성능 변화를 확인합니다. 또한, 테스트 데이터셋의 예측 결과를 시각화하여 모델의 분류 성능을 시각적으로 평가합니다.

### 실행 방법
1. Google Colab에서 새로운 노트를 생성합니다.
2. 제공된 코드를 Colab 노트에 복사하고 셀을 실행합니다.
3. 데이터셋을 `/mnt/lion`와 `/mnt/tiger` 경로에 업로드합니다.
4. 모든 셀을 순차적으로 실행하여 모델을 훈련 및 평가합니다.

### 주의 사항
- 데이터셋의 경로가 정확한지 확인하십시오.
- 훈련 중 Colab 세션이 중단되지 않도록 주의하십시오.