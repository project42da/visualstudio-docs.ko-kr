---
title: "toString 메서드(Boolean) | Microsoft Docs"
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
ms.assetid: c46b43c0-6946-407a-b0e0-49cba90e226a
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# toString 메서드(Boolean)
개체를 나타내는 문자열을 반환합니다.  
  
## 구문  
  
```  
  
boolean.toString()  
```  
  
## 매개 변수  
 `boolean`  
 필수 요소.  문자열 표현을 가져올 개체입니다.  
  
## 반환 값  
 부울 값이 `true`이면 "true"를 반환합니다.  그렇지 않으면 "false"를 반환합니다.  
  
## 설명  
  
## 예제  
 다음 예제는 **toString** 메서드의 사용 예를 보여 줍니다.  
  
```javascript  
var s = new Boolean(0);  
document.write(s.toString());  
  
// Output: false;  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]