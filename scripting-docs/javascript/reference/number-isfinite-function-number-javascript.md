---
title: "Number.isFinite 함수(Number)(JavaScript) | Microsoft Docs"
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
ms.assetid: 41a91408-09d1-49f2-b7a0-6da105e2ed8e
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# Number.isFinite 함수(Number)(JavaScript)
값을 한정 숫자인지 여부를 나타내는 부울 값을 반환합니다.  
  
## 구문  
  
```  
Number.isFinite(numValue)   
```  
  
## 반환 값  
 값이 `NaN`, `+∞` 또는 `-∞`이면 `false`이고, 그렇지 않으면 `true`입니다.  
  
## 설명  
  
## 예제  
  
```javascript  
// Returns true  
Number.isFinite(100)  
Number.isFinite(-100)  
Number.isFinite(100 / 3)  
  
// Returns false  
Number.isFinite(Number.NaN)  
Number.isFinite(Infinity)  
Number.isFinite("100")  
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **적용 대상**: [Number 개체](../../javascript/reference/number-object-javascript.md)