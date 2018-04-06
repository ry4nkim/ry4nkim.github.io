---
title: "[iOS / Swift4] Alamofire 사용하기"
layout: post
date: 2018-04-06 13:40
image: /assets/images/github-logo.png
headerImage: fal9se
tag:
- iOS
- Swift
category: blog
author: ry4nkim
description: Alamofire 란? Alamofire는 iOS와 OS X에서 사용하기 위한 Swift 기반의 HTTP 네트워킹 라이브러리 입니다.
---

## Summary:

Alamofire 란?
- Alamofire는 iOS와 OS X에서 사용하기 위한 Swift 기반의 HTTP 네트워킹 라이브러리 입니다.

### Index
- [Preparations](#preparations)
- [Get Started](#get-started)

---
## Preparations

Alamofire를 사용하기 위해서는 CocoaPods가 필수적으로 설치되어 있어야 합니다.

CocoaPods Install
{% highlight raw %}
$ sudo gem install cocoapods
{% endhighlight %}

## Get Started

{% highlight raw %}
$ pod init
{% endhighlight %}

{% highlight raw %}
source 'https://github.com/CocoaPods/Specs.git'
platform :ios, '10.0'
use_frameworks!

target '<b><Your Target Name></b>' do
    <b>pod 'Alamofire', '~> 4.7'</b>
end
{% endhighlight %}

{% highlight raw %}
$ pod install
{% endhighlight %}