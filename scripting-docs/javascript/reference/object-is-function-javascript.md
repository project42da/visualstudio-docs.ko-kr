---
title: "Object.is 함수(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 6e2f6c6d-7cd2-47c4-a513-3ba53988d27d
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# Object.is 함수(JavaScript)
두 값이 같은 값인지를 나타내는 값을 반환합니다.  
  
## 구문  
  
```javascript  
Object.is(value1, value2)  
```  
  
#### 매개 변수  
 `value1`  
 필수 요소.  테스트할 첫 번째 값입니다.  
  
 `value2`  
 필수 요소.  테스트할 두 번째 값입니다.  
  
## 반환 값  
 값이 동일한 값이면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## 설명  
 \=\= 연산자와 달리 `Object.is`는 값을 테스트할 때 형식을 강제 변환하지 않습니다.  
  
 `Object.is`에 의해 적용되는 비교는 `Object.is`가 `Number.isNaN`을 `NaN`과 동일한 값으로 처리한다는 점을 제외하고 \=\=\= 연산자에 의해 적용되는 비교와 유사합니다.  \+0과 \-0도 다른 값으로 처리합니다.  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]