---
title: "스크립트 문제 해결(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "자동 형식 변환"
  - "스크립트 문제 해결"
ms.assetid: 0e0545d9-44e5-4179-befc-99a882c5c672
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 스크립트 문제 해결(JavaScript)
프로그래밍 언어에는 놀라운 부분이 있습니다.  예를 들어 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]의 `null` 값은 C 또는 C\+\+ 언어의 `Null` 값과 같이 동작하지 않습니다.  
  
 다음에 설명되어 있는 사항은 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립트를 작성하면서 겪게 될 수 있는 문제입니다.  
  
## 구문 오류  
 스크립트를 작성할 때 세부 정보에 주의해야 합니다.  예를 들어 문자열은 따옴표로 묶어야 합니다.  
  
## 스크립트 해석 순서  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 해석은 웹 브라우저의 HTML 구문 분석 프로세스의 일부입니다.  문서에서 \<HEAD\> 태그 안에 스크립트를 삽입하면 이 스크립트는 \<BODY\> 태그의 어떤 부분보다 먼저 해석됩니다.  \<BODY\> 태그에서 만들어지는 개체는 \<HEAD\> 요소가 구문 분석될 때는 존재하지 않으므로 스크립트에서 조작할 수 없습니다.  
  
> [!NOTE]
>  이러한 동작은 Internet Explorer에만 해당됩니다.  ASP와 WSH의 실행 모델은 다른 호스트와 마찬가지로 다릅니다.  
  
## 자동 형식 강제 변환  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]는 자동 강제 변환이 가능한 자유로운 형식의 언어입니다.  형식이 다르면 값도 달라야 함에도 불구하고 다음 예제 식은 **true**로 평가됩니다.  
  
```javascript  
"100" == 100;  
false == 0;  
```  
  
 형식과 값이 모두 같은지 확인하려면 완전 같음 연산자\(\=\=\=\)를 사용합니다.  다음은 모두 false로 평가됩니다.  
  
```javascript  
"100" === 100;  
false === 0;  
```  
  
## 연산자 우선 순위  
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)는 식을 평가하는 동안 연산이 수행될 때 결정됩니다.  다음 예제에서는 식에서 빼기가 먼저 나오더라도 곱하기가 빼기 이전에 수행됩니다.  
  
```javascript  
theRadius = aPerimeterPoint - theCenterpoint * theCorrectionFactor;  
```  
  
## 개체에 for...in 루프 사용  
 [for…in](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md) 루프를 사용하여 개체의 속성을 반복할 때 개체 필드가 루프 카운터 변수에 할당되는 순서를 예측할 수 있거나 제어할 수 없습니다.  언어의 구현 방법에 따라서도 그 순서가 달라질 수 있습니다.  
  
## with 키워드  
 [with](../../javascript/reference/with-statement-javascript.md) 문은 지정된 개체에 이미 존재하는 속성에 액세스하는 데는 편리하지만 개체에 속성을 추가하는 데는 사용할 수 없습니다.  개체에서 새로운 속성을 만들려면 개체를 명확하게 참조해야 합니다.  
  
## this 키워드  
 `this` 키워드를 개체 정의 내에 사용하여 개체 자체를 참조하도록 하지만, 함수가 개체 정의가 아닌 경우에는 `this` 또는 비슷한 키워드를 현재 실행 중인 함수를 참조하는 데 사용할 수 없습니다.  함수를 개체에 메서드로 할당하는 경우에는 함수 내에서 `this` 키워드를 사용하여 개체를 참조할 수 있습니다.  
  
## Internet Explorer에서 스크립트를 작성하는 스크립트 작성하기  
 해석기에서 \<\/SCRIPT\> 태그를 발견하면 현재 스크립트가 종료됩니다.  "\<\/SCRIPT\>" 자체를 표시하려면 "\<\/SCR"과 "IPT\>"처럼 두 개 이상의 문자열로 다시 작성하고 이 문자열을 작성하는 문에서 함께 연결할 수 있습니다.  
  
## Internet Explorer에서 암시적 창 참조  
 두 개 이상의 창이 한 번에 열릴 수 있기 때문에 암시적 창 참조는 현재 창을 가리킵니다.  다른 창에 대해서는 명시적 참조를 사용해야 합니다.