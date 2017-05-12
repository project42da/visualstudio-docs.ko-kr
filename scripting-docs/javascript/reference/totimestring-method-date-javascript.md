---
title: "toTimeString 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "toTimeString"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "toTimeString 메서드"
ms.assetid: a4a8c0f2-55a9-4e84-94c3-f0a547fb04b5
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# toTimeString 메서드(Date)(JavaScript)
시간을 문자열 값으로 반환합니다.  
  
## 구문  
  
```  
  
objDate. toTimeString( )  
```  
  
## 설명  
 필수 `objDate` 참조는 `Date` 개체입니다.  
  
 `toTimeString` 메서드는 현재 표준 시간대의 시간이 들어 있는 문자열 값을 반환합니다.  
  
## 예제  
 다음 예제에서 시간은 1970년 1월 1일 자정 UTC 이후 2000밀리초로 설정되고 작성됩니다.  
  
```javascript  
var aDate = new Date();  
     aDate.setTime(2000);  
     document.write(aDate.toTimeString());  
  
// Output depends on the time in the current time zone.  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## 참고 항목  
 [toDateString 메서드\(Date\)](../../javascript/reference/todatestring-method-date-javascript.md)   
 [toLocaleTimeString 메서드\(Date\)](../../javascript/reference/tolocaletimestring-method-date-javascript.md)