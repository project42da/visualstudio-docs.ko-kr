---
title: "toString 메서드(String) | Microsoft Docs"
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
ms.assetid: 56178c6e-cb08-4b34-824c-f63505379952
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# toString 메서드(String)
문자열을 나타내는 문자열을 반환합니다.  
  
## 구문  
  
```  
  
string.toString()  
```  
  
## 매개 변수  
 `string`  
 필수 요소.  문자열로 표현할 배열입니다.  
  
## 반환 값  
 문자열의 문자열 표현입니다.  
  
## 예제  
 다음 예제에서는 문자열을 사용한 **toString** 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var string = "this is a test";  
var strStr = string.toString();  
document.write(strStr);  
  
// Output: this is a test  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]