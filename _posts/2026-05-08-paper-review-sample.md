---
layout: post
title: "[논문 리뷰] (Sample)BCS Theory of Superconductivity (1957)"
date: 2026-05-08 14:00:00 +0900
description: Bardeen, Cooper, Schrieffer의 초전도 이론 논문을 읽고 핵심 아이디어를 정리했습니다.
tags: [superconductivity, condensed-matter, BCS, Cooper-pair]
categories: papers
related_posts: false
toc:
  sidebar: left
---

## 논문 정보

| 항목 | 내용 |
|------|------|
| 제목 | Theory of Superconductivity |
| 저자 | J. Bardeen, L. N. Cooper, J. R. Schrieffer |
| 저널 | Physical Review, **108**, 1175 (1957) |
| DOI | [10.1103/PhysRev.108.1175](https://doi.org/10.1103/PhysRev.108.1175) |

---

## 핵심 아이디어

BCS 이론의 핵심은 전자-포논 상호작용으로 인해 페르미 면 근방의 전자들이 **쿠퍼 쌍(Cooper pair)**을 형성한다는 것이다.

### 쿠퍼 쌍

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

