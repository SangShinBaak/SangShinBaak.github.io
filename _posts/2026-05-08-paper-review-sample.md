---
layout: post
title: "[논문 리뷰](Reading) A Monte Carlo Formulation of Bogoliubov Theory (2000)"
date: 2026-05-30 14:00:00 +0900
description: TWA와 관련된 논문을 읽는중입니다.
tags: [Truncated Wigner Approximation, condensed-matter, Stochastic]
categories: papers
related_posts: false
toc:
  sidebar: left
---

## 논문 정보

| 항목 | 내용 |
|------|------|
| 제목 | A Monte Carlo Formulation of Bogoliubov Theory |
| 저자 | A. Sinatra, Y. Castin, C. Lobo |
| 저널 | 	Journal of Modern Optics **47**, 2629-2644 (2000). |
| DOI | [10.1080/09500340008232186](https://doi.org/10.1080/09500340008232186) |

---

## 핵심 아이디어

**NCB**와 **TWA**를 사용해 finite temperature Bose gas를 **brownian motion**으로 계산함.

<!-- ### 쿠퍼 쌍

운동량 $\mathbf{k}$와 $-\mathbf{k}$, 스핀이 반대인 두 전자가 효과적인 인력으로 묶인다.

$$
|\text{BCS}\rangle = \prod_{\mathbf{k}} \left( u_k + v_k \, c^\dagger_{\mathbf{k}\uparrow} c^\dagger_{-\mathbf{k}\downarrow} \right) |0\rangle
$$

여기서 $|u_k|^2 + |v_k|^2 = 1$ (규격화 조건).

### 에너지 갭

BCS 이론의 가장 중요한 예측 중 하나는 페르미 면 근방에 에너지 갭 $\Delta$이 열린다는 것이다.

$$
\Delta = 2\hbar\omega_D \, e^{-1/N(0)V}
$$

- $\omega_D$ : 디바이 진동수
- $N(0)$ : 페르미 면에서의 상태 밀도
- $V$ : 전자-전자 인력 결합 상수

---

## 인상 깊었던 점

에너지 갭이 결합 상수 $V$에 대해 **비해석적(non-analytic)**인 형태를 가진다는 점이 흥미롭다. 이는 섭동론으로는 절대 얻을 수 없는 결과임을 의미한다.

---

## 개인 메모

- 쿠퍼 쌍의 크기(결맞음 길이 $\xi$)와 자기장 침투 깊이의 관계를 추가로 공부할 것
- Ginzburg-Landau 이론과의 연결도 흥미로움
-->
---

## 논문 내용
### Introduction
GP equation은 condensate와 noncondensed particles 사이의 상호작용을 무시해서 구한다. 이는 transition temperature 보다 아주 낮은 저온에서 그럴싸한 이야기다.
하지만 실제로는 상호작용을 무시할 수 없는 경우들이 있다.
 - Time-dependent properties:
   - **modulation of trapping potential**에 의해 유도된 **collective modes**
   - **thermdynamically unstable states** like *vortices* or *dark solitons*
 - Time-independent properties:
   - theremal equilibrium properties: 
     - *spatial density of noncondensed particles* 
     - *thermal fluctuations of number of condensed particles*

저온에서는 **Bogoliubov Theory** 사용 -- 이 방법은 *noncondensate particle*을 기술하는 field operator의 *quadratization*과 *Bogoliubov transformation*에 의존. 
더 큰 온도범위에서는 **Hatree-Fock-Bogoliubov (HFB) method**사용 -- system density의 Gaussian ansatz에 기반한 variational method.

일반적으론 계산이 너무 복잡함.
Alternative formulation of Bogoliubov theory is given here.
특징 : Wigner representation of density matrix에 의존. 
finite temperature에서 system의 steady-state Wigner distribution을 sample하기 위한 Monte Carlo simulation에 위존.
이 방법은 **Gaussian** density operator를 sample하도록 해주기 때문에, thermal equilibrium 또는 time dependent에서 *Bogoliubov*와 *HFB* 모두 적용할 수 있다.

### Bogoliubov theory conserving the total number of particles
여기서는 짧게 NCB를 소개한다.
해밀토니안은
$$ H =\int \mathrm{d}^3r \hat{\Psi}^\dagger\Big(-\frac{\hbar^2}{2m}\nabla^2+U\Big)\hat{\Psi} +\frac{g}{2}\hat{\Psi}^{\dagger2}\hat{\Psi}^2 $$
여기서 one-body density operator $\rho_1$에 대해 가장 큰 eigenvalue $N_0$를 갖는 state를 $|\phi_{\rm ex}\rangle$이라고 하자:
$$\rho_1|\phi_{\rm ex}\rangle = N_0|\phi_{\rm ex}\rangle $$
BEC가 존재한다고 가정하자, 그러면 $\phi_{\rm ex}$눈 condensate wavefuction이고, $N_0\simeq N$.
Field operator $\hat{\Psi}$를 condensate와 noncondensed modes의 합으로 쪼개자:
$$ \hat{\Psi} = \phi_{\rm ex}\hat{a}_{\rm ex}+\hat{\psi} $$
여기서 $\hat{a}_{\rm ex}$는 condensate particle annihilation operator. 