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
- [Alamofire JSON Request Example](#alamofire-json-request-example)

---
## Preparations

Alamofire를 사용하기 위해서는 CocoaPods가 필수적으로 설치되어 있어야 합니다.

CocoaPods Install
{% highlight raw %}
$ sudo gem install cocoapods
{% endhighlight %}

## Get Started

1.&nbsp;터미널을 실행하고 cd 명령어로 Alamofire를 사용할 Xcode 프로젝트 경로로 이동합니다.
{% highlight raw %}
$ cd <Your Project Path>
{% endhighlight %}

2.&nbsp;이동한 후, 아래 명령어를 입력하면 프로젝트 경로 내에 Podfile이 생성됩니다.
{% highlight raw %}
$ pod init
{% endhighlight %}

3.&nbsp;생성된 Podfile 을 Text Editor 로 열어 아래와 같이 수정해줍니다.
{% highlight raw %}
source 'https://github.com/CocoaPods/Specs.git'
platform :ios, '10.0'
use_frameworks!

target '<Your Target Name>' do
    pod 'Alamofire', '~> 4.7'
end
{% endhighlight %}

4.&nbsp;Podfile을 수정 및 저장한 뒤, 아래 명령을 입력하여 Alamofire 라이브러리를 설치합니다.
{% highlight raw %}
$ pod install
{% endhighlight %}

5.&nbsp;설치 후 프로젝트 내에 새로 생성된 `<Your Project Name>.xcworkspace` 파일을 Xcode로 실행합니다.

6.&nbsp;ViewController.swift 파일에 맨 위줄 라인에 `import Alamofire` 을 추가하여 정상적으로 빌드되는지 확인합니다.

## Alamofire JSON Request Example

{% highlight swift %}
Alamofire.request(
            "http://<Your URL>",
            method: .get,
            parameters: [:],
            encoding: URLEncoding.default,
            headers: ["Content-Type":"application/json", "Accept":"application/json"]
            )
            .validate(statusCode: 200..<300)
            .responseJSON {
                response in
                if let JSON = response.result.value {
                    print(JSON)
                }
            }
{% endhighlight %}
