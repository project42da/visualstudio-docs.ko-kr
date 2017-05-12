---
title: "toString 메서드(Array) | Microsoft Docs"
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
ms.assetid: 71fbea85-3e00-41b0-b167-25e4281e5e8a
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# toString 메서드(Array)
배열을 나타내는 문자열을 반환합니다.  
  
## 구문  
  
```  
  
array.toString()  
```  
  
## 매개 변수  
 `array`  
 필수 요소.  문자열로 표현할 배열입니다.  
  
## 반환 값  
 배열의 문자열 표현입니다.  
  
## 설명  
 `Array`의 요소는 문자열로 변환됩니다.  결과로 나온 문자열은 연결되고 쉼표로 구분됩니다.  
  
## 예제  
 다음 예제는 배열을 사용한 **toString** 메서드의 사용 예를 보여 줍니다.  
  
```javascript  
var arr = [1, 2, 3, 4];  
var s = arr.toString();  
document.write(s);  
  
// Output: 1,2,3,4  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]