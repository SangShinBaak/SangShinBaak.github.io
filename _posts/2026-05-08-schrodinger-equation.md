---
layout: post
title: "슈뢰딩거 방정식: 유도와 해석"
date: 2026-05-08 12:00:00 +0900
description: 양자역학의 핵심 방정식인 슈뢰딩거 방정식을 유도하고, 그 물리적 의미를 살펴봅니다.
tags: [quantum-mechanics, wave-function, operators]
categories: concepts
related_posts: false
toc:
  sidebar: left
---

## 개요

슈뢰딩거 방정식(Schrödinger equation)은 양자역학에서 계의 상태가 시간에 따라 어떻게 변화하는지를 기술하는 방정식이다. 고전역학의 뉴턴 방정식에 대응되는 양자역학의 운동 방정식으로 볼 수 있다.

---

## 시간 의존 슈뢰딩거 방정식

시간 의존 슈뢰딩거 방정식(TDSE)은 다음과 같다.

$$
i\hbar \frac{\partial}{\partial t} \Psi(\mathbf{r}, t) = \hat{H} \Psi(\mathbf{r}, t)
$$

여기서:
- $\hbar = h / 2\pi$ : 환산 플랑크 상수
- $\Psi(\mathbf{r}, t)$ : 파동함수(wave function)
- $\hat{H}$ : 해밀토니안 연산자(Hamiltonian operator)

### 해밀토니안 연산자

퍼텐셜 $V(\mathbf{r}, t)$ 하의 입자에 대한 해밀토니안은 운동에너지와 퍼텐셜에너지의 합이다.

$$
\hat{H} = \hat{T} + \hat{V} = -\frac{\hbar^2}{2m}\nabla^2 + V(\mathbf{r}, t)
$$

따라서 TDSE를 명시적으로 쓰면:

$$
i\hbar \frac{\partial \Psi}{\partial t} = \left[ -\frac{\hbar^2}{2m}\nabla^2 + V(\mathbf{r}, t) \right] \Psi
$$

---

## 시간 독립 슈뢰딩거 방정식

퍼텐셜이 시간에 무관한 경우 $V = V(\mathbf{r})$, 변수 분리법을 사용할 수 있다.

$$
\Psi(\mathbf{r}, t) = \psi(\mathbf{r}) \cdot e^{-iEt/\hbar}
$$

이를 TDSE에 대입하면 시간 독립 슈뢰딩거 방정식(TISE)을 얻는다.

$$
\hat{H} \psi(\mathbf{r}) = E\psi(\mathbf{r})
$$

이것은 해밀토니안의 **고유값 방정식**이다. 에너지 $E$는 고유값(eigenvalue), $\psi$는 고유함수(eigenfunction)이다.

---

## 파동함수의 확률 해석 (Born 규칙)

파동함수 자체는 직접 관측할 수 없다. Born의 확률 해석에 따르면:

$$
|\Psi(\mathbf{r}, t)|^2 \, d^3r
$$

는 시간 $t$에 위치 $\mathbf{r}$ 근방의 부피 $d^3r$ 에서 입자를 발견할 **확률**이다.

따라서 전체 공간에 대한 적분은 1이어야 한다 (규격화 조건):

$$
\int_{-\infty}^{\infty} |\Psi(\mathbf{r}, t)|^2 \, d^3r = 1
$$

---

## 간단한 예: 무한 퍼텐셜 우물

$0 \le x \le L$ 구간에 갇힌 입자 ($V=0$), 그 외 구간에서 $V=\infty$인 경우.

경계 조건 $\psi(0) = \psi(L) = 0$ 을 적용하면 에너지 고유값과 고유함수는:

$$
E_n = \frac{n^2 \pi^2 \hbar^2}{2mL^2}, \quad n = 1, 2, 3, \ldots
$$

$$
\psi_n(x) = \sqrt{\frac{2}{L}} \sin\left(\frac{n\pi x}{L}\right)
$$

에너지가 **양자화(quantization)**됨을 확인할 수 있다.

---

## 참고

- Griffiths, D. J., *Introduction to Quantum Mechanics*, 3rd ed.
- Sakurai, J. J., *Modern Quantum Mechanics*, 2nd ed.
