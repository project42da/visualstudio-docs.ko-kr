---
title: "constructor 속성(Date) | Microsoft Docs"
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
ms.assetid: 5db153a1-788b-4a61-bfc8-2d2ec38f36ea
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# constructor 속성(Date)
날짜를 만드는 함수를 지정합니다.  
  
## 구문  
  
```  
  
date.constructor  
```  
  
## 설명  
 필수 `date`는 date 개체의 이름입니다.  
  
 `constructor` 속성은 초기 설정을 가지는 모든 초기 설정 개체의 멤버입니다.  `constructor` 속성은 특정 개체의 인스턴스를 구성하는 함수에 대한 참조를 포함합니다.  
  
## 예제  
 다음 예제에서는 constructor 속성을 사용하는 방법을 보여 줍니다.  
  
```javascript  
var x = new Date("Hi");  
  
if (x.constructor == Date)  
    document.write("Object is a date.");  
  
// Output:  
// Object is a date.  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]