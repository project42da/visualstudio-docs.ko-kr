---
title: "getTimezoneOffset 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getTimeZoneOffset"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "getTimezoneOffset 메서드"
  - "표준 시간대[Visual Studio]"
ms.assetid: 58ee22b0-4688-45bd-a337-cc23119b09ce
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# getTimezoneOffset 메서드(Date)(JavaScript)
로컬 컴퓨터의 시간과 UTC\(협정 세계 표준시\) 간의 차이를 분 단위로 가져옵니다.  
  
## 구문  
  
```  
  
dateObj.getTimezoneOffset()   
```  
  
#### 매개 변수  
 필수 `dateObj` 참조는 `Date` 개체입니다.  
  
## 반환 값  
 현재 컴퓨터\(클라이언트 컴퓨터 또는 이 메서드가 서버 스크립트에서 호출되는 경우 서버 컴퓨터\)의 시간과 UTC 간의 차이를 분 단위로 반환합니다.  현재 컴퓨터의 현지 시간이 태평양 일광 절약 시간처럼 UTC보다 느리면 양수가 되고 일본에서처럼 UTC보다 빠르면 음수가 됩니다.  로스앤젤레스의 클라이언트가 뉴욕의 서버에 12월 1일에 연결한 경우 `getTimezoneOffset`은 클라이언트에서 실행되었으면 480을 반환하고 서버에서 실행되었으면 300을 반환합니다.  
  
## 설명  
  
## 예제  
 다음 예제에서는 `getTimezoneOffset` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var date =  new Date();  
var minutes = date.getTimezoneOffset();  
  
if (minutes < 0)  
    document.write(minutes / 60 + " hours after UTC");  
else  
    document.write(minutes / 60 + " hours before UTC");  
  
// Output (for example, where local time is PST):   
7 hours before UTC  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getTime 메서드\(Date\)](../../javascript/reference/gettime-method-date-javascript.md)