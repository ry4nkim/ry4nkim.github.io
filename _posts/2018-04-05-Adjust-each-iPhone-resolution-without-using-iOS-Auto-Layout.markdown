---
title: "[iOS / Swift4] Auto Layout 사용하지 않고 각각의 iPhone 해상도 맞추기"
layout: post
date: 2018-04-06 10:30
image: /assets/images/markdown.jpg
headerImage: false
tag:
- iOS
- Swift
category: blog
author: ry4nkim
description: 처음 iOS를 공부하다 보면 하나의 Storyboard만으로 여러 iPhone 기기들의 해상도를 대응하는 Auto Layout 이란 기능에 접근하기 어려울 것이다. 왜냐하면 Auto Layout 기능을 사용하기 위해서는 Object 간의 제약(Constraints) 조건을 수학적 방정식으로 설계해야 하기 때문일 것이다. 이를 어려워하는 초보 iOS 개발자들을 위해 Auto Layout 기능을 사용하지 않고 각각의 iPhone 해상도 맞추는 방법을 알려드리고자 한다.
---

## Summary:

처음 iOS를 공부하다 보면 하나의 Storyboard만으로 여러 iPhone 기기들의 해상도를 대응하는 Auto Layout 이란 기능에 접근하기 어려울 것이다.

왜냐하면 Auto Layout 기능을 사용하기 위해서는 Object 간의 제약(Constraints) 조건을 수학적 방정식으로 설계해야 하기 때문일 것이다.

이를 어려워하는 초보 iOS 개발자들을 위해 Auto Layout 기능을 사용하지 않고 각각의 iPhone 해상도 맞추는 방법을 알려드리고자 한다.

### Index
- [Preparations](#preparations)
- [Code](#code)

---
## Preparations

각각의 iPhone 크기 별로 Storyboard를 생성해둔다.

## Code

{% gist ry4nkim/fbec12a30fdc8f664dcbd932e0011cd7 %}