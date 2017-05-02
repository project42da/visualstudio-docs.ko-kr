---
title: "getDate 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getDate"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Date 개체"
  - "날짜, 일 반환"
  - "getDate 메서드"
ms.assetid: 67e7f07c-dd46-4b42-82d6-e53e4bd33703
caps.latest.revision: 20
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 20
---
# getDate 메서드(Date)(JavaScript)
로컬 시간을 사용하여 날짜\(월 기준\)를 가져옵니다.  
  
## 구문  
  
```  
  
dateObj.getDate()   
```  
  
#### 매개 변수  
 필수 `dateObj` 참조는 `Date` 개체입니다.  
  
## 반환 값  
 날짜\(월 기준\)를 나타내는 1에서 31까지의 정수입니다.  
  
## 설명  
 UTC\(협정 세계 표준시\)를 사용하여 날짜\(월 기준\)를 가져오려면 `getUTCDate` 메서드를 사용합니다.  
  
## 예제  
 다음 예제에서는 `getDate` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var date = new Date("Jan 01, 2001");  
var str = "Today's date is: ";  
   str += (date.getMonth() + 1) + "/";  
   str += date.getDate() + "/";  
   str += date.getFullYear();  
document.write(str);  
  
// Output: Today's date is: 1/1/2001  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getUTCDate 메서드\(Date\)](../../javascript/reference/getutcdate-method-date-javascript.md)   
 [setDate 메서드\(Date\)](../../javascript/reference/setdate-method-date-javascript.md)   
 [setUTCDate 메서드\(Date\)](../../javascript/reference/setutcdate-method-date-javascript.md)