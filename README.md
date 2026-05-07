# Fashion Style Classification & Recommendation System

>  우수상 — 2024 데이터 크리에이터 캠프 (주최: 과학기술정보통신부 · NIA)

CNN-based fashion style image classification with GradCAM XAI analysis,
combined with an item-based collaborative filtering recommendation system.

---

## My Contributions *(4-person team)*

| Area | What I did |
|------|------------|
| **Image Classification** | Implemented ResNet18 fine-tuning for 30+ fashion style categories |
| **XAI Analysis** | Applied GradCAM to generate heatmaps and interpret model classification decisions |

---

## Results

| Task | Metric | Score |
|------|--------|-------|
| Image Classification | Validation Accuracy | **61.51%** |
| Recommendation System | Accuracy | **92.11%** |
| Recommendation System | F1 Score | **90.37%** |

---

## Pipeline

    Fashion Image Data (30+ style categories × Male/Female)
              ↓
    [YOLO] Person detection & cropping
              ↓
    [ResNet18] ← My contribution
    Style classification (CrossEntropyLoss, Adam, 200 epochs)
              ↓
    [GradCAM] ← My contribution
    Heatmap visualization — model decision interpretation
              ↓
    [item-based CF] Weighted similarity ensemble
    similarity = 0.1 × item + 0.3 × image + 0.6 × survey
              ↓
    Fashion preference prediction

---

## XAI: GradCAM Heatmap

Applied GradCAM to visualize which regions of the clothing image
the model focuses on when making classification decisions.
Confirmed that the model attends to clothing features rather than background.

---

## Training Config

| Parameter | Value |
|-----------|-------|
| Model | ResNet18 |
| Epochs | 200 |
| Batch Size | 32 |
| Learning Rate | 0.001 |
| Optimizer | Adam |
| Loss | CrossEntropyLoss |
| Early Stopping | patience=20 |

---

## Tech Stack

`Python` `PyTorch` `ResNet18` `GradCAM` `Scikit-learn` `Pandas`

---

## Team Contributions *(4-person team)*

| Role | Area |
|------|------|
| **Image Classification + XAI (Me)** | ResNet18 training, GradCAM heatmap analysis |
| Preprocessing | YOLO-based person cropping, data augmentation |
| Recommendation | item-based CF, weighted similarity optimization |
| Statistics & EDA | Chi-square, Cramér's V, Random Forest feature selection |

---

## Limitations & Next Steps

- 30+ class classification with limited data per class → accuracy ceiling
- GradCAM limited to last convolutional layer interpretation
- Recommendation cold-start problem for new users not addressed

---

---

# 👗 패션 스타일 분류 및 추천 시스템

> 🏆 우수상 — 2024 데이터 크리에이터 캠프 (주최: 과학기술정보통신부 · NIA)

---

## 본인 담당 역할

| 역할 | 내용 |
|------|------|
| **이미지 분류** | ResNet18 fine-tuning으로 30개 이상 패션 스타일 분류 모델 구현 |
| **XAI 분석** | GradCAM 히트맵 적용으로 모델 판단 근거 시각화 및 해석 |

---

## 성능

| 태스크 | 지표 | 값 |
|--------|------|----|
| 이미지 분류 | Validation Accuracy | **61.51%** |
| 추천 시스템 | Accuracy | **92.11%** |
| 추천 시스템 | F1 Score | **90.37%** |

---

## 학습 설정

| 파라미터 | 값 |
|----------|----|
| 모델 | ResNet18 |
| Epochs | 200 |
| Batch Size | 32 |
| Learning Rate | 0.001 |
| Optimizer | Adam |
| Loss | CrossEntropyLoss |
| Early Stopping | patience=20 |

---

## XAI: GradCAM 히트맵

모델이 패션 스타일을 분류할 때 이미지의 어느 부위에 집중하는지
GradCAM 히트맵으로 시각화했습니다.
배경이 아닌 의상 영역에 집중함을 확인했습니다.

---

## 팀 구성 (4인)

| 역할 | 담당 |
|------|------|
| **이미지 분류 + XAI (본인)** | ResNet18 학습, GradCAM 히트맵 분석 |
| 전처리 | YOLO 객체 탐지 기반 인물 크롭, 데이터 증강 |
| 추천 시스템 | item-based CF, 가중치 최적화 |
| 통계 분석 | 카이제곱, Cramér's V, Random Forest 피처 선택 |

---

## 한계 및 개선 방향

- 30개 이상 클래스 분류 → 클래스당 데이터 부족으로 정확도 한계
- GradCAM이 마지막 합성곱 레이어 기준 해석에 한정
- 추천 시스템 신규 사용자 cold-start 문제 미해결
