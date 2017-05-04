---
title: "setYear 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "setYear"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "setYear 메서드"
  - "Year 메서드"
ms.assetid: 36431050-e0ec-45ee-830d-0d7c20e207ea
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# setYear 메서드(Date)(JavaScript)
`Date` 개체의 연도 값을 설정합니다.  
  
## 구문  
  
```  
  
dateObj.setYear(numYear)   
```  
  
## 매개 변수  
 `dateObj`  
 필수 요소.  임의의 `Date` 개체입니다.  
  
 `numYear`  
 필수 요소.  1900년에서 1999년까지는 현재 연도에서 1900을 뺀 숫자 값입니다.  해당 범위를 벗어나는 날짜의 경우 4자리 숫자 값입니다.  
  
## 설명  
 이 메서드는 이전 방식이며 이전 버전과의 호환성을 유지하기 위해서만 사용됩니다.  대신 `setFullYear` 메서드를 사용합니다.  
  
 `Date` 개체의 연도를 1997년으로 설정하려면 **setYear\(97\)**를 호출하고  2010년으로 설정하려면 **setYear\(2010\)**를 호출하세요.  마지막으로 연도를 0부터 99 사이의 값으로 설정하려면 `setFullYear` 메서드를 사용하세요.  
  
> [!NOTE]
>  [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 버전 1.0에서 `setYear`는 연도 값에 상관없이 `numYear`의 연도 값에 1900을 더한 결과 값을 사용합니다.  예를 들어 연도를 1899로 설정하면 `numYear`는 \-1이고 2000으로 설정하면 `numYear`는 100입니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getFullYear 메서드\(Date\)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [getUTCFullYear 메서드\(Date\)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [getYear 메서드\(Date\)](../../javascript/reference/getyear-method-date-javascript.md)   
 [setFullYear 메서드\(Date\)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setUTCFullYear 메서드\(Date\)](../../javascript/reference/setutcfullyear-method-date-javascript.md)