---
title: "toString 메서드(Number) | Microsoft Docs"
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
ms.assetid: 07c3484b-d9d8-4451-a2be-88a19a081966
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# toString 메서드(Number)
숫자를 나타내는 문자열을 반환합니다.  
  
## 구문  
  
```  
  
number.toString()  
```  
  
## 매개 변수  
 `number`  
 필수 요소.  문자열로 표현할 숫자입니다.  
  
## 반환 값  
 숫자의 문자열 표현입니다.  
  
## 예제  
 다음 예제에서는 숫자를 사용한 **toString** 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var number = 234.567;  
var s = number.toString();  
document.write(s.length);  
  
// Output: 7  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]