---
title: "charCodeAt 메서드(String)(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "charCodeAt"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "charCodeAt 메서드"
ms.assetid: 5b0290a7-ee4d-4738-a909-c02ef64a2f1a
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# charCodeAt 메서드(String)(JavaScript)
지정한 위치에 있는 문자의 유니코드 값을 반환합니다.  
  
## 구문  
  
```  
  
strObj. charCodeAt(index)  
```  
  
## 매개 변수  
 `strObj`  
 필수 요소.  임의의 `String` 개체 또는 문자열 리터럴입니다.  
  
 `index`  
 필수 요소.  원하는 문자의 0부터 시작하는 인덱스입니다.  지정된 인덱스에 문자가 없으면 `NaN`이 반환됩니다.  
  
## 설명  
  
## 예제  
 다음 예제에서는 `charCodeAt` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var str = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";   
document.write(str.charCodeAt(str.length - 1));  
  
// Output: 90   
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## 참고 항목  
 [String.fromCharCode 함수](../../javascript/reference/string-fromcharcode-function-javascript.md)