---
title: "Symbol.for 함수(JavaScript) | Microsoft Docs"
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
ms.assetid: 27db15f3-9108-4892-8f89-e84031729cb6
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# Symbol.for 함수(JavaScript)
지정된 키에 대한 기호를 반환하거나 키가 없는 경우 새 키를 사용하여 새 기호 개체를 만듭니다.  
  
## 구문  
  
```vb  
Symbol.for(key);  
```  
  
#### 매개 변수  
 `key`  
 필수.  설명으로도 사용되는 기호에 대한 키입니다.  
  
## 설명  
 이 메서드는 전체 기호 레지스트리에서 해당 기호를 검색합니다.  기호를 문자열로 직렬화하는 경우 전역 기호 레지스트리를 사용하여 특정 문자열 맵이 모든 조회에 대해 올바른 기호를 보여주도록 합니다.  
  
## 예제  
  
```javascript  
var sym = Symbol.for("desc");  
  
console.log(sym.toString());  
  
// Two different object references.  
console.log(Symbol("symbol") === Symbol.for("symbol");)  
// Single object reference.   
console.log(Symbol.for("symbol") === Symbol.for("symbol");)  
  
// Output:  
// Symbol(desc);  
// false  
// true  
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]