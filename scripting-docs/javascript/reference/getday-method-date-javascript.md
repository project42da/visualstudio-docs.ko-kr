---
title: "getDay 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getDay"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "GetDay 메서드"
  - "Date 개체"
  - "날짜, 주 반환"
ms.assetid: 27be7168-3dce-41c9-ae69-6280b7984c2e
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# getDay 메서드(Date)(JavaScript)
로컬 시간을 사용하여 요일을 가져옵니다.  
  
## 구문  
  
```  
  
dateObj. getDay()   
```  
  
#### 매개 변수  
 필수 `dateObj` 참조는 `Date` 개체입니다.  
  
## 반환 값  
 요일을 나타내는 0에서 6까지의 정수입니다\(일요일은 0, 토요일은 6\).  
  
## 설명  
 UTC\(협정 세계 표준시\)를 사용하여 요일 값을 가져오려면 `getUTCDay` 메서드를 사용하세요.  
  
 다음 예제에서는 `getDay` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var date = new Date("Saturday, February 9, 2008");  
day = date.getDay();  
document.write(day);  
  
// Output: 6  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getUTCDay 메서드\(Date\)](../../javascript/reference/getutcday-method-date-javascript.md)