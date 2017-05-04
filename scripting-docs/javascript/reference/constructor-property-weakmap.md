---
title: "constructor 속성(WeakMap) | Microsoft Docs"
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
ms.assetid: 1e3f9333-ce75-4d32-9b14-fbe81fd73dfb
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# constructor 속성(WeakMap)
`WeakMap` 개체를 만드는 함수를 지정합니다.  
  
## 구문  
  
```javascript  
weakmap.constructor  
```  
  
## 설명  
 필수 `weakmap`는 `WeakMap` 개체의 이름입니다.  
  
 `constructor` 속성은 초기 설정을 가지는 모든 초기 설정 개체의 멤버입니다.  여기에는 `Global` 및 `Math` 개체를 제외한 모든 내장 JavaScript 개체가 포함됩니다.  `constructor` 속성은 특정 개체의 인스턴스를 구성하는 함수에 대한 참조를 포함합니다.  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]