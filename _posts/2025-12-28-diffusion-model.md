---
layout: post
title: "Diffusion Model"
subtitle: "Generative Model"
date: 2025-12-28 11:00:00 +0900
categories: [Generative Model]
background: '/img/home-bg.png' 
use_math: true
---

## 1. Introduction
**diffusion model**은 최근 생성모델들의 핵심기술이다.

![](/assets/images/2025-12-28-diffusion-model/2025-12-28-16-46-32.png)
<br>
맑은 물에 잉크를 떨어뜨리면 확산 과정은 예측하기 어렵지만
시간이 지나면 **uniform**한 분포를 이룰 것이다.

이런 엔트로피의 증가과정을 딥러닝을 통해 학습하여 **uniform**한 분포에서 다시
한 점으로 잉크를 모아보고자 하는 것이 **diffusion model**의 개념이다.

---

## 2. Core Concept
**diffusion Model**은 데이터에 노이즈를 점진적으로 추가했다가, 이를 다시 복원하는 과정을 학습한다.
![](/assets/images/2025-12-28-diffusion-model/2025-12-28-17-08-23.png)

### 2-1) Forward Diffusion Process (Noising)
![](/assets/images/2025-12-28-diffusion-model/2025-12-28-17-27-00.png)
**Forward Process** 또는 **Diffusion Process**라고 불리는 이 과정은 
$x_0$부터 $x_T$까지 **Gaussian noise**를 점진적으로 추가하는 과정이며 학습은 하지 않는다.

### 2-2) Reverse Diffusion Process (Denoising)

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
* **https://www.calibraint.com/blog/beginners-guide-to-diffusion-models**
* 