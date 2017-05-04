---
title: "valueOf 메서드(Boolean) | Microsoft Docs"
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
ms.assetid: ac6ad343-7663-406a-a2b7-4cc5025ca3d6
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# valueOf 메서드(Boolean)
지정한 부울의 원시 값을 반환합니다.  
  
## 구문  
  
```  
  
boolean.valueOf()  
```  
  
## 반환 값  
 부울의 원시 값\(true 또는 false\)입니다.  
  
## 설명  
 다음 코드에서는 이 메서드의 사용법을 보여 줍니다.  
  
```javascript  
var bool = new Boolean("true");  
var s = bool.valueOf();  
document.write(s);  
  
// Output: true  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]