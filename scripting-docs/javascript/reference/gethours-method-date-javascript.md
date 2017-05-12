---
title: "getHours메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getHours"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Date 개체"
  - "GetHours 메서드"
  - "Hours 메서드"
ms.assetid: c3936496-a213-4d15-b308-d53926ed310c
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# getHours메서드(Date)(JavaScript)
로컬 시간을 사용하여 날짜의 시 값을 가져옵니다.  
  
## 구문  
  
```  
  
dateObj.getHours()   
```  
  
#### 매개 변수  
 필수 `dateObj` 참조는 `Date` 개체입니다.  
  
## 반환 값  
 자정부터 시작하는 시 값을 나타내는 0부터 23까지의 정수입니다.  시간이 오전 1:00:00 이전이면 0이 반환됩니다.  시간을 지정하지 않고 `Date` 개체를 만든 경우 기본적으로 시 값은 0입니다.  
  
## 설명  
 UTC\(협정 세계 표준시\)를 사용하여 시 값을 가져오려면 `getUTCHours` 메서드를 사용하세요.  
  
## 예제  
 다음 예제에서는 `getHours` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var date = new Date("1/1/2001");  
document.write(date.getHours());  
document.write("<br/>");  
  
date.setTime(50000000);  
document.write(date.getHours());  
  
// Output:  
// 0   
// 5  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getUTCHours 메서드\(Date\)](../../javascript/reference/getutchours-method-date-javascript.md)   
 [setHours 메서드\(Date\)](../../javascript/reference/sethours-method-date-javascript.md)   
 [setUTCHours 메서드\(Date\)](../../javascript/reference/setutchours-method-date-javascript.md)