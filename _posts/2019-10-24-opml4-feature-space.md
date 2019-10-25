---
layout: post
title: "Feature space"
date: 2019-10-24 18:43:00 +0800
categories: one-page-learning
---

![alt](/img/figures/ml/drawing/feature-space.png)

게임에서 캐릭터를 고를 때는 체력, 지력, 마나 등등의 status bar를 본다. 두 캐릭터의 status가 같다는 것은 두 캐릭터가 같은 능력치를 가진다는 뜻이다. 캐릭터마다 고유하게 갖는 것이 status이므로, status를 보면 그게 어느 캐릭터인지를 알 수 있다.

머신러닝에서 고양이 사진 쥐 사진 등등의 데이터도 그와 마찬가지로 표현한다. 고양이의 특징1이 5만큼 있고, 특징2는 10만큼 있고, 특징3은 20만큼 있고, ... 그런 식이다. 고양이는 고양이의 특징이 있고, 쥐는 쥐만의 특징이 있다. 특징이 완전히 같은 두 사진은 서로 구분할 수 없다. 고양이 사진이든 쥐 사진이든, N차원짜리 좌표축의 한 점으로 표현한다. 두 점의 거리가 가까우면 비슷한 것이고, 두 점의 거리가 멀수록 다른 것이다.

고양이의 특징을 다섯 가지로 두면 그것을 5차원의 vector로 표현할 수 있다. Feature space라고 부른다. 5차원의 좌표축은, 단지 좌표축 개수가 다섯개 $$(x, y, z, u, v)$$라는 뜻이다. 체력이 5만큼, 마나가 10 만큼, 지능이 20만큼, 공격력이 15만큼, 방어력이 50만큼 ... 그런 식이다.

차원 수가 높을수록 더 많은 특징을 표현할 수 있고, 그러면 더욱 정밀한 구분이 가능하다. 굳이 안 따져도 될 특징 (눈 색깔 이라든지...) 때문에 차원 수가 무의미하게 높아지면 구분에 방해가 되기도 한다.

The feature space is like a status window of an RPG game. When you pick an avatar, there would be multiple status bars (e.g., HP, MP, etc) to represent each character of the avatar. If two characters have the same status, then there is no way to distinguish the two avatars.

In terms of machine learning, each status bar corresponds to each axis ($$x, y, z, u, v$$). The character is completely represented by its status of five dimensions.

The same metaphor works when it comes to classification tasks. Machines can distinguish if the image is a cat or rat by looking at each status bar. If the two objects have the same status, then the machine says both images are identical.
