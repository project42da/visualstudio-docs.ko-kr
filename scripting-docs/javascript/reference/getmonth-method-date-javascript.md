---
title: "getMonth 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getMonth"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Date 개체"
  - "날짜, 월 값"
  - "Month 메서드"
  - "GetMonth 메서드"
ms.assetid: c20dd8ba-1d78-42f1-8717-ed3dfd2362dd
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# getMonth 메서드(Date)(JavaScript)
로컬 시간을 사용하여 월을 가져옵니다.  
  
## 구문  
  
```  
  
dateObj.getMonth()   
```  
  
#### 매개 변수  
 필수 `dateObj` 참조는 `Date` 개체입니다.  
  
## 반환 값  
 `getMonth` 메서드는 0\(1월\)부터 11\(12월\)까지의 정수를 반환합니다.  "Jan 5, 1996"을 사용하여 생성된 `Date`의 경우 `getMonth`는 0을 반환합니다.  
  
## 설명  
 UTC\(협정 세계 표준시\)를 사용하여 월 값을 가져오려면 `getUTCMonth` 메서드를 사용하세요.  
  
## 예제  
 다음 예제에서는 `getMonth` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var date = new Date("1/1/2001");  
document.write(date.getMonth());  
  
// Output: 0  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getUTCMonth 메서드\(Date\)](../../javascript/reference/getutcmonth-method-date-javascript.md)   
 [setMonth 메서드\(Date\)](../../javascript/reference/setmonth-method-date-javascript.md)   
 [setUTCMonth 메서드\(Date\)](../../javascript/reference/setutcmonth-method-date-javascript.md)