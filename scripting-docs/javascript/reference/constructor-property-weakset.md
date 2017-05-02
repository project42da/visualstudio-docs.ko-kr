---
title: "constructor 속성(WeakSet) | Microsoft Docs"
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
ms.assetid: 234e7104-9b78-4bfa-8f77-2bc44a570928
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# constructor 속성(WeakSet)
`WeakSet`을 만드는 함수를 지정합니다.  
  
## 구문  
  
```javascript  
weakset.constructor  
```  
  
## 설명  
 필수 `weakset`은 집합의 이름입니다.  
  
 `constructor` 속성은 프로토타입이 있는 모든 개체의 프로토타입 멤버입니다.  여기에는 `Global` 및 `Math` 개체를 제외한 모든 내장 JavaScript 개체가 포함되어 있습니다.   `constructor` 속성은 해당 특정 개체의 인스턴스를 구성하는 함수에 대한 참조를 포함합니다.  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]