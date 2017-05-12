---
title: "isFinite 함수(JavaScript) | Microsoft Docs"
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
  - "isFinite"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "유한 숫자"
  - "isFinite 메서드"
ms.assetid: ea9287d2-892f-496b-86b7-f9196868d5cf
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# isFinite 함수(JavaScript)
제공된 숫자가 유한한지 여부를 확인합니다.  
  
## 구문  
  
```  
isFinite(number)   
```  
  
## 설명  
 필수 `number` 인수는 임의의 숫자 값입니다.  
  
 `isFinite` 함수는 `number`가 `NaN`, 음의 무한대 또는 양의 무한대 이외의 값이면 `true`를 반환하고,  이 세 경우에는 **false**를 반환합니다.  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Global 개체](../../javascript/reference/global-object-javascript.md)  
  
## 참고 항목  
 [isNaN 함수](../../javascript/reference/isnan-function-javascript.md)