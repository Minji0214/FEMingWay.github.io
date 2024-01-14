---
title: "오류일기: 이미지 인코딩 오류"
description: "nextImage에서 갑자기 엑박이 뜹니다."
date: 2021-05-01
update: 2021-05-01
tags:
  - error
  - next
series: "Getting started your blog with gatsby-starter-hoodie"
---

장바구니 썸네일이 갑자기 안나온다. 왜그럴까..?

기존에 몇몇 썸네일 이미지가 인코딩 되어 내려오지 않아서

강제로 인코딩을 해주었는데

이번엔 인코딩 되어 내려온 애들이 강제 인코딩으로 인해 두번 인코딩 되는 오류가 발생한 것이다.

어떻게 보면 저번 오류의 사이드 이펙트랄까..?

인코딩 된 url, 되지않은 url의 기준은 결국 %특수문자로 가르기로 했다.

그렇게 인코딩 되지 않았을 경우에만 인코딩 하는걸로 …

이런게 코딩인가….야매인가…요량만 늘어나는…..

```jsx
//인코딩된 이미지와, 인코딩되지 않은 이미지가 섞여있음
const thumbImg = item.product?.thumb_img.includes("%")
  ? item.product?.thumb_img
  : encodeURI(item.product?.thumb_img)
```

나는 이럴때 좀 현타가 온다.

마켓플레이스를 운영하다보면 이런 작업들이 많은데

이런 코드만 짜다가 평생 이런 코드만 짜는 개발자로 전락해버리는건 아닐까…하는

아니야..아니야 …
