---
layout: post
title: "Feature space"
date: 2019-10-24 18:43:00 +0800
categories: one-page-learning
---

![alt](/img/figures/ml/drawing/feature-space.png)

게임에서 캐릭터를 고를 때는 체력, 지력, 마나 등등의 스탯 (status) bar를 본다. 두 캐릭터의 스탯 이 같다는 것은 두 캐릭터가 같은 능력치를 가진다는 뜻이다. 반대로 말해서, 스탯을 보면 그게 어느 캐릭터인지를 알 수 있다는 뜻이다.

머신러닝에서 고양이 사진 쥐 사진을 구분하는 것도 그와 마찬가지다. 고양이의 특징1이 얼만큼 있고, 특징2는 얼만큼 있고, 특징3은 얼만큼 있고, ... 그런 식이다. 고양이는 고양이의 특징이 있고, 쥐는 쥐만의 특징이 있다.

고양이의 특징을 다섯 가지로 보겠다면 5차원의 vector로 표현할 수 있다. 그것을 Feature space라고 부른다. 5차원의 좌표축은, 단지 좌표축 개수가 다섯개라는 뜻이다. 체력이 5만큼, 마나가 10 만큼, 지능이 20만큼, ... 그런 식이다.

어떤 데이터를 기계가 인식하는 방식은 그와 같다. 그게 고양이 사진이든 쥐 사진이든, N차원짜리 좌표축의 한 점으로 표현한다. 두 점의 거리가 가까우면 비슷한 것이고, 두 점의 거리가 멀수록 다른 것이다.


The feature space is like a status window of RPG game. When you pick an avatar, there are multiple status bars (e.g., HP, MP, etc) to represent each characteristic of the avatar. If two characters have the same status, then there is no way to distinguish the two avatars.

In terms of machine learning, each status bar corresponds to each axis ($$x, y, z, u, v$$). The character is completely represented by its status of five dimensions.

The same metaphor works when it comes to classification task. Machines can distinguish if the image is cat or rat by looking at each status bar. If the two objects have the same status, then the machine says both of images are identical.
