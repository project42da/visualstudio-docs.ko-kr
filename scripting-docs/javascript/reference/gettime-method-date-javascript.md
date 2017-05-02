---
title: "getTime 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getTime"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "GetTime 메서드"
  - "time 메서드"
ms.assetid: f0da1d4e-337c-497d-9205-093defbc6d3d
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# getTime 메서드(Date)(JavaScript)
시간 값을 밀리초 단위로 가져옵니다.  
  
## 구문  
  
```  
  
dateObj.getTime()   
```  
  
#### 매개 변수  
 필수 `dateObj` 참조는 `Date` 개체입니다.  
  
## 반환 값  
 1970년 1월 1일 자정과 `Date` 개체의 시간 값 사이의 시간을 밀리초 단위로 반환합니다.  날짜 범위는 1970년 1월 1일 자정에서 약 285,616년입니다.  음수는 1970 이전의 날짜를 나타냅니다.  
  
## 설명  
 날짜와 시간을 여러 번 계산할 때는 밀리초 값에 해당하는 변수를 일, 시 또는 분으로 정의할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```javascript  
var minute = 1000 * 60;  
var hour = minute * 60;  
var day = hour * 24;  
```  
  
 `getTime` 메서드를 사용하는 방법에 대한 자세한 내용은 [날짜 및 시간 계산\(JavaScript\)](../../javascript/calculating-dates-and-times-javascript.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 `getTime` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var minute = 1000 * 60;  
var hour = minute * 60;  
var day = hour * 24;  
  
date = new Date("1/1/2001");  
var time = date.getTime();  
  
document.write(Math.round(time / day) + " days from 1/1/1970 to 1/1/2001");  
  
// Output: 11323 days from 1/1/1970 to 1/1/2001  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [setTime 메서드\(Date\)](../../javascript/reference/settime-method-date-javascript.md)