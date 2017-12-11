---
title: "스크립트 문제 해결(JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- automative type conversion
- troubleshooting scripts
ms.assetid: 0e0545d9-44e5-4179-befc-99a882c5c672
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7e0193e6dc0996d5e2d0d3df7103c7705d29477
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="troubleshooting-your-scripts-javascript"></a>스크립트 문제 해결(JavaScript)
프로그래밍 언어에는 특이한 부분이 있습니다. 예를 들어 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]의 `null` 값은 C 또는 C++ 언어의 `Null` 값과 다르게 작동합니다.  
  
 다음은 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립트를 작성할 때 실행할 수 있는 문제 영역 중 일부입니다.  
  
## <a name="syntax-errors"></a>구문 오류  
 스크립트를 작성할 때는 세부 사항에 주의해야 합니다. 예를 들어 문자열은 따옴표로 묶어야 합니다.  
  
## <a name="order-of-script-interpretation"></a>스크립트 해석 순서  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 해석은 웹 브라우저의 HTML 구문 분석 프로세스의 일부입니다. 문서에서 \<HEAD> 태그 내에 스크립트를 배치하는 경우 \<BODY> 태그 부분 이전에 해석됩니다. \<BODY> 태그에 만든 개체가 있는 경우 \<HEAD>가 구문 분석될 때 존재하지 않으며 스크립트로 조작할 수 없습니다.  
  
> [!NOTE]
>  이 동작은 Internet Explorer에 고유합니다. ASP 및 WSH에는 다른 실행 모델이 있습니다(다른 호스트처럼).  
  
## <a name="automatic-type-coercion"></a>자동 형식 강제 변환  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]은(는) 자동 강제 변환이 가능한 느슨한 형 언어입니다. 유형이 다른 값이 같지 않더라도 다음 예제의 식은 **true**로 평가됩니다.  
  
```JavaScript  
"100" == 100;  
false == 0;  
```  
  
 유형 및 값이 동일한지 확인하려면 완전 같음 연산자(===)를 사용합니다. 다음은 모두 평가 결과가 false입니다.  
  
```JavaScript  
"100" === 100;  
false === 0;  
```  
  
## <a name="operator-precedence"></a>연산자 우선 순위  
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)는 식 평가 중에 연산이 수행되는 시기를 결정합니다. 다음 예제에서는 빼기가 표현식에서 먼저 표시되더라도 곱하기가 빼기 전에 수행됩니다.  
  
```JavaScript  
theRadius = aPerimeterPoint - theCenterpoint * theCorrectionFactor;  
```  
  
## <a name="using-forin-loops-with-objects"></a>개체에 for...in 루프 사용  
 [for...in](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md) 루프로 개체의 속성을 반복할 때는 개체의 필드가 루프 카운터 변수에 할당되는 순서를 예측하거나 제어할 수 없습니다. 또한 언어의 다른 구현에 따라 순서가 다를 수 있습니다.  
  
## <a name="with-keyword"></a>with 키워드  
 [with](../../javascript/reference/with-statement-javascript.md) 문은 지정된 개체에 이미 있는 속성에 액세스하는 데 편리하지만 객체에 속성을 추가하는 데는 사용할 수 없습니다. 개체에 새 속성을 만들려면 해당 개체를 구체적으로 참조해야 합니다.  
  
## <a name="this-keyword"></a>this 키워드  
 개체 정의 내에서 `this` 키워드를 사용하여 개체 자체를 참조할지라도, 해당 기능이 개체 정의가 아닌 경우 `this` 또는 유사한 키워드를 사용하여 현재 실행 중인 함수를 참조할 수 없습니다. 함수가 개체에 메서드로 할당되는 경우 개체를 참조하기 위해 함수 내에서 `this` 키워드를 사용할 수 있습니다.  
  
## <a name="writing-a-script-that-writes-a-script-in-internet-explorer"></a>Internet Explorer에서 스크립트를 작성하는 스크립트 작성  
 \</SCRIPT> 태그는 인터프리터가 발견하면 현재 스크립트를 종료합니다. "\</SCRIPT>" 자체를 표시하려면 "\</SCR" 및 "IPT>"와 같이 이 문자열을 적어도 두 개의 문자열로 다시 작성합니다. 그러면 이 문자열을 작성하는 문에서 함께 연결할 수 있습니다.  
  
## <a name="implicit-window-references-in-internet-explorer"></a>Internet Explorer에서 암시적 창 참조  
 한 번에 둘 이상의 창을 열 수 있으므로 암시적 창 참조는 현재 창을 가리킵니다. 다른 창에 대해서는 명시적 참조를 사용해야 합니다.