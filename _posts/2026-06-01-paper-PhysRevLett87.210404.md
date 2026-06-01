---
layout: post
title: "[논문 리뷰](Reading) Classical-Field Method for Time Dependent Bose-Einstein Condensed Gases (2001)"
date: 2026-06-01 14:00:00 +0900
math: true
math_engine: mathjax
description: TWA와 관련된 논문을 읽는중입니다.
tags: [Truncated Wigner Approximation, BEC, NCB, Thermal Equilibrium]
categories: papers
related_posts: true
toc:
  sidebar: left
---

## 논문 정보

| 항목 | 내용 |
|------|------|
| 제목 | Classical-Field Method for Time Dependent Bose-Einstein Condensed Gases |
| 저자 | A. Sinatra, Y. Castin, C. Lobo |
| 저널 | Physical Review Letters **87**, 210404 (2001). |
| DOI | [10.1103/PhysRevLett.87.210404](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.87.210404) |

---
## 핵심 아이디어
초기 **thermal equilibrium**에서 *perturbed* 된 BEC의 **time evolution**을 $N$-body density operator의 **Wigner represention**을 이용해 표현.
어떻게 **NCB**안에서 Wigner distribution을 샘플링하는 *random classical fields*를 얻을 수 있는지 알려준다.

특징:
 - *time-independent*인 경우에는 NCB와 완전히 동등.
 - *time-dependent*인 경우에는 Bogoliubov approach와는 다르게, classical field evolution이 condensate 및 noncondensate 모두 *nonlinear*하기 때문에, 더 긴 시간동안 적용 가능하다.

## 논문 내용
### NCB
#### Field operator를 condensate와 orthogonal part로 쪼개기
일단 Bose-gas의 (normalised) field operator를 다음과 같이 써준다:  

$$ \hat{\Psi}(\vec{r}) = \phi(\vec{r})\hat{a}_\phi+\hat{\psi}(\vec{r}). $$

여기서 condensate annihilation operator $$\hat{a}_\phi$$를 *condensate phase operator* $$\hat{A}_\phi$$와 condensate number operator $$\hat{N}_0$$를 이용해 표현한다:

$$ \hat{a}_\phi = \hat{A}_\phi\hat{N}_0^{1/2}$$

condensate phase operator는 **거의 unitary**이다:
$$ \hat{A}_\phi^\dagger\hat{A}_\phi + |0\rangle\langle0| = \hat{A}_\phi^\dagger\hat{A}_\phi  = \mathbb{1} $$
그리고 이는 noncondensate $$\hat{\psi}$$와도 commute.

총 입자수가 보존되려면 condensate가 하나 늘어나면 noncondensate가 하나 줄어들어야 한다. 따라서, $$\Lambda = \hat{A}_\phi^\dagger\hat{\psi}$$를 가지고 이야기한다. 

zeroth order에서 나오는 GP Hamiltonian은

$$ H_{\rm GP} = -\frac{\hbar^2}{2m}\nabla^2+U+gN|\phi|^2-\mu $$

quadratic Hamiltonian은
$$ \hat{H}_{\rm quad} = \int \ud^3\vec{r} \frac{1}{2} \mathbb{\Lambda}\mathcal{L}\mathbb{\Lambda} $$



## 개인 메모
사실 $$\hat{A}$$를 phase operator로 가정하면 문제가 있다. 대표적으로 위에서 $$\Lambda$$ 에서 condensate를 하나 줄이려면 commute 하면 안된다.
