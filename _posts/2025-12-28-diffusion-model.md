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

![](/assets/images/2025-12-28-diffusion-model/2025-12-28-23-59-19.png)
<br>
어떤 시점 t에 대해서 $x_{t-1}$ 이미지에서 $x_t$이미지로 넘어가는 step에서 수학적으로 스케줄링 된 랜덤한 **noise**를 이미지에 붙인다.
이때 아주 작은 값인 $\beta$를 이용해서 기존 이미지의 픽셀 값을 깎고, 노이즈를 넣는 가중 합을 실행하게 된다.

그리고 그러한 전 과정을 $x_0$에 대한 **Joint Distribution**으로 나타낼 수 있다.

![](/assets/images/2025-12-28-diffusion-model/2025-12-29-00-05-30.png)
<br>
이때 Forward Process는 학습에 사용하지 않으니 $x_0$에서 $x_t$까지 한 번에 생성할 수 있는 [Reparameterization Trick](https://velog.io/@strongdeutan00/Reparameterization-Trick-for-Diffusion-Model)을 사용할 수 있다.


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
* **https://www.youtube.com/watch?v=uFoGaIVHfoE**