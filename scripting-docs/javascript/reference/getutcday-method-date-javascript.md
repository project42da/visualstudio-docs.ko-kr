---
title: "getUTCDay 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getUTCDay"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Date 개체"
  - "날짜, UTC "
  - "UTC 날짜, 반환"
  - "getUTCDay 메서드"
ms.assetid: 2fceb5b0-6f77-4919-82c3-0877fd55bacb
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# getUTCDay 메서드(Date)(JavaScript)
UTC\(협정 세계 표준시\)를 사용하여 요일을 가져옵니다.  
  
## 구문  
  
```  
  
dateObj.getUTCDay()   
```  
  
#### 매개 변수  
 필수 `dateObj` 참조는 `Date` 개체입니다.  
  
## 반환 값  
 요일을 나타내는 0\(일요일\)에서 6\(토요일\)까지의 정수를 반환합니다.  
  
## 설명  
 로컬 시간을 사용하여 요일 값을 가져오려면 `getDate` 메서드를 사용합니다.  
  
## 예제  
 다음 예제에서는 `getUTCDay` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var date = new Date("2/6/2001");  
var day = date.getUTCDay();  
document.write(day);  
  
// Output: 2  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getDay 메서드\(Date\)](../../javascript/reference/getday-method-date-javascript.md)