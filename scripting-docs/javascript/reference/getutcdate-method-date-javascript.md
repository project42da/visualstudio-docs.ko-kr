---
title: "getUTCDate 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getUTCDate"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Date 개체"
  - "날짜, UTC"
  - "UTC 날짜, 반환"
  - "getUTCDate 메서드"
ms.assetid: 9e4c763f-c94c-44c9-9684-cb632d75b62e
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# getUTCDate 메서드(Date)(JavaScript)
UTC\(협정 세계 표준시\)를 사용하여 날짜\(월 기준\)를 가져옵니다.  
  
## 구문  
  
```  
  
dateObj.getUTCDate()   
```  
  
#### 매개 변수  
 필수 `dateObj` 참조는 `Date` 개체입니다.  
  
## 반환 값  
 날짜\(월 기준\)를 나타내는 1에서 31까지의 정수를 반환합니다.  
  
## 설명  
 현지 시간을 사용하여 날짜를 가져오려면 `getDate` 메서드를 사용하세요.  
  
## 예제  
 다음 예제에서는 `getUTCDate` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var date = new Date("1/23/2001");  
document.write(date.getUTCDate());  
  
// Output: 23  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getDate 메서드\(Date\)](../../javascript/reference/getdate-method-date-javascript.md)   
 [setDate 메서드\(Date\)](../../javascript/reference/setdate-method-date-javascript.md)   
 [setUTCDate 메서드\(Date\)](../../javascript/reference/setutcdate-method-date-javascript.md)