---
layout: post
title: "Diffusion Model이란 무엇인가?"
subtitle: "이미지 생성 모델의 혁신, Diffusion Model 간단 정리"
date: 2025-12-22 18:00:00 +0900
categories: [AI, Generative Models]
background: '/img/posts/01.jpg' 
---

## Diffusion Model (확산 모델)

**Diffusion Model**은 최근 생성형 AI 분야에서 가장 주목받는 모델 중 하나입니다. 주로 텍스트를 입력받아 고품질의 이미지를 생성하는 데 사용됩니다 (예: Stable Diffusion, DALL-E 2).

### 기본 원리

Diffusion Model의 학습 과정은 크게 두 단계로 나눌 수 있습니다.

1.  **Forward Process (확산 과정)**: 원본 이미지에 노이즈를 조금씩 추가하여 완전한 노이즈 상태로 만듭니다.
2.  **Reverse Process (역방향 과정)**: 노이즈 상태에서 노이즈를 점진적으로 제거하여 원래의 이미지(또는 새로운 이미지)를 복원해 나가는 과정을 학습합니다.

이 모델은 마치 잉크가 물에 퍼지는 것(Diffusion)을 역으로 돌려 잉크 방울을 다시 모으는 것과 비슷한 원리라고 생각하시면 됩니다.

### 주요 특징

*   **고품질 생성**: GAN(Generative Adversarial Networks)에 비해 학습이 안정적이고 다양한 이미지를 생성할 수 있습니다.
*   **단계적 생성**: 노이즈를 단계적으로 제거해가며 이미지를 구체화하기 때문에, 중간 과정을 제어하기 용이합니다.

이 포스트는 카테고리 추가 예시를 위해 작성되었습니다. 상단 Front Matter의 `categories` 부분을 참고해주세요!
