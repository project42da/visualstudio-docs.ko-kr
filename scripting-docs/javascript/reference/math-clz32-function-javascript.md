---
title: "Math.clz32 함수(JavaScript) | Microsoft Docs"
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
ms.assetid: 34615d7a-6d88-4ab5-a696-7e496caa51db
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# Math.clz32 함수(JavaScript)
숫자의 32비트 이진 표현에서 앞에 있는 0비트의 수를 반환합니다.  
  
## 구문  
  
```  
  
Math.clz32(  
number  
)   
```  
  
## 설명  
 `number`이\(가\) 0이면 결과는 32가 됩니다.  `number`의 32비트 이진 인코딩 중 최상위 비트가 1이면 결과는 0이 됩니다.  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **적용 대상**: [Math 개체](../../javascript/reference/math-object-javascript.md)