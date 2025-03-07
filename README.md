# MNIST CNN Experiment

## 📌 프로젝트 개요
이 프로젝트는 **CNN을 활용하여 MNIST 손글씨 숫자 인식을 수행하는 실험**입니다.
- 데이터 증강 기법을 활용하여 학습 데이터의 다양성을 증가시켰으며,
- 학습률을 랜덤으로 설정하는 기법을 적용하여 모델의 최적화 성능을 향상시키는 실험을 진행했습니다.

### 🔹 주요 내용
- **CNN (Convolutional Neural Network) 기반 MNIST 숫자 분류 모델 구현**
- **랜덤 학습률(Random Learning Rate) 적용**
- **ImageDataGenerator를 활용한 데이터 증강 적용**
- **Early Stopping 및 ReduceLROnPlateau 콜백 적용**

---

## 🛠 사용한 기술
- **Python, TensorFlow, Keras**를 사용하여 딥러닝 모델 구축
- **Conv2D, MaxPooling2D, BatchNormalization, LeakyReLU** 등 다양한 신경망 레이어 활용
- **Adam Optimizer & 랜덤 학습률 조정**을 통한 최적화 실험
- **EarlyStopping & ReduceLROnPlateau**로 모델 성능 최적화
- **Matplotlib을 활용한 학습 과정 및 예측 결과 시각화**

---

## 📂 데이터셋
- **MNIST (Modified National Institute of Standards and Technology)**
- 60,000개의 학습 데이터와 10,000개의 테스트 데이터
- 28x28 픽셀의 손글씨 숫자 (0~9)

---

## 📊 모델 구조
```python
model = Sequential([
    Conv2D(32, kernel_size=(3, 3), activation='relu', input_shape=(28, 28, 1)),
    BatchNormalization(),
    MaxPooling2D(pool_size=(2, 2)),
    Conv2D(64, kernel_size=(3, 3), activation='relu'),
    BatchNormalization(),
    MaxPooling2D(pool_size=(2, 2)),
    Flatten(),
    Dense(128),
    LeakyReLU(alpha=0.1),
    Dropout(0.5),
    Dense(10, activation='softmax')
])
```

---

## 🏆 실험 결과
- **최종 테스트 정확도:** `99.27%`
- **랜덤 학습률이 적용된 CNN 모델이 안정적인 학습 과정 유지**
- **데이터 증강을 활용한 모델 성능 개선 확인**

### 🔹 학습 정확도 그래프
![Model Accuracy](Model Accuracy.png)

### 🔹 학습 손실 그래프
![Model Loss](Model Loss.png)

### 🔹 예측 결과 예시
- 샘플 이미지 (예: `7`)
  ![Sample Image](Sample Image.png)
- 예측 확률 분포
  ![Prediction Probabilities](Prediction Probabilities.png)

## 📌 GitHub 분류
🚀 **AI & Machine Learning**

