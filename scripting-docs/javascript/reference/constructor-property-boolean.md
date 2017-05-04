---
title: "constructor 속성(Boolean) | Microsoft Docs"
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
ms.assetid: b67ca875-23c6-4687-a5ce-1cdd25d1c923
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# constructor 속성(Boolean)
부울을 만드는 함수를 지정합니다.  
  
## 구문  
  
```  
  
boolean.constructor([[value])  
```  
  
#### 매개 변수  
 `boolean`  
 부울의 이름입니다.  
  
 `value`  
 선택 사항입니다.  부울의 값을 지정합니다.  1 또는 0의 숫자나 "true" 또는 "false"의 문자열일 수 있습니다.  
  
## 설명  
 `constructor` 속성은 부울 개체의 인스턴스를 구성하는 함수에 대한 참조를 포함합니다.  
  
## 예제  
 다음 예제에서는 constructor 속성의 사용법을 보여 줍니다.  
  
```javascript  
var x = new Boolean("true");  
  
if (x.constructor == Boolean)  
    document.write("Object is a Boolelan.");  
  
// Output:  
// Object is a Boolean.  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]