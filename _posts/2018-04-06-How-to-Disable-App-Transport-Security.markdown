---
title: "[iOS] App Transport Security 해제 방법"
layout: post
date: 2018-04-06 16:10
image: /assets/images/github-logo.png
headerImage: true
tag:
- iOS
category: blog
author: ry4nkim
description: App Transport Security(ATS) 란? App Transport Security 는 iOS 9 부터 도입된 네트워크 보안 기능입니다. 이 기능은 HTTPS 연결을 제외한 보안에 취약한 네트워크 프로토콜의 연결을 차단시킵니다. 이로인해 기존에 많이 쓰이던 HTTP 프로토콜의 연결을 하지 못하게 되었습니다.
---

## Summary:

App Transport Security(ATS) 란?
- App Transport Security 는 iOS 9 부터 도입된 네트워크 보안 기능입니다. 
- 이 기능은 HTTPS 연결을 제외한 보안에 취약한 네트워크 프로토콜의 연결을 차단시킵니다.
- 이로인해 기존에 많이 쓰이던 HTTP 프로토콜의 연결을 하지 못하게 되었습니다.

App Transport Security HTTP 연결 오류 메시지

{% highlight raw %}
App Transport Security has blocked a cleartext HTTP resource(http://) load since it is insecure.
Temporary exceptions can be configured via your app's Info.plist file.
{% endhighlight %}

{% highlight raw %}
App Transport Security가 안전하지 않기 때문에 cleartext HTTP(http://) 리소스 로드를 차단했습니다.
임시 예외는 앱의 Info.plist 파일을 통해 구성할 수 있습니다.
{% endhighlight %}

---
## How to Disable ATS

앱 개발을 위해 HTTP 프로토콜의 연결이 꼭 필요로 하다면 Info.plist 파일을 통해 App Transport Security를 해제할 수 있습니다.

Info.plist
{% highlight ruby %}
<key>NSAppTransportSecurity</key>
<dict>
    <key>NSAllowsArbitraryLoads</key>
    <true/>
    <key>NSAllowsArbitraryLoadsForMedia</key>
    <true/>
    <key>NSAllowsArbitraryLoadsInWebContent</key>
    <true/>
</dict>
{% endhighlight %}