---
layout: post
title: "Diffusion Model"
subtitle: "Generative Model"
date: 2025-12-28 11:00:00 +0900
categories: [Generative Model]
background: '/img/home-bg.png' 
---

## 1. Introduction
**diffusion model**은 최근 생성모델들의 핵심기술이다.

![](/assets/images/2025-12-28-diffusion-model/2025-12-28-16-46-32.png)
맑은 물에 잉크를 떨어뜨리면 확산 과정은 예측하기 어렵지만
시간이 지나면 **uniform**한 분포를 이룰 것이다.

이런 엔트로피의 증가과정을 딥러닝을 통해 학습하여 **uniform**한 분포에서 다시
한 점으로 잉크를 모아보고자 하는 것이 **diffusion model**의 개념이다.

---

## 2. Core Concept
*diffusion Model*은 데이터에 노이즈를 점진적으로 추가했다가, 이를 다시 복원하는 과정을 학습한다.

### 1) Forward Diffusion Process (Noising)
데이터 $x_0$에서 시작하여 가우시안 노이즈를 단계적으로 추가하여 완전한 노이즈 $x_T$를 만드는 과정이다.
- **수식:** $q(x_t | x_{t-1}) = \mathcal{N}(x_t; \sqrt{1-\beta_t}x_{t-1}, \beta_t I)$

### 2) Reverse Diffusion Process (Denoising)
모델이 학습하는 핵심 부분으로, 노이즈 $x_t$에서 이전 단계 $x_{t-1}$을 예측하여 원본 데이터를 복원한다.
- **Goal:** $p_\theta(x_{t-1} | x_t)$를 정교하게 예측하는 신경망 학습

---

## 3. Diffusion Model의 장점
* **Training Stability:** GAN처럼 적대적 학습이 아니기에 학습이 안정적이다.
* **Sample Quality:** 높은 다양성과 고품질의 이미지를 생성한다.
* **Mode Collapse 방지:** 데이터 분포의 모든 영역을 골고루 학습한다.

---

## 4. 아키텍처 (Architecture)
주로 **U-Net** 구조를 사용하며, 각 단계에서 노이즈가 얼마나 섞여 있는지를 파악하기 위해 **Time Embedding** 기법을 적용합니다.



---


## References
* 
* 