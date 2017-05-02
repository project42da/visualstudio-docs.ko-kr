---
title: "getUTCSeconds 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getUTCSeconds"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "UTC 시간, 반환"
  - "seconds 메서드"
  - "getUTCSeconds 메서드"
ms.assetid: 2d8ea7dc-79f8-4a9b-b2ab-732db2bcd5fd
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# getUTCSeconds 메서드(Date)(JavaScript)
초를 가져옵니다는 `Date` 협정 세계 표준시 \(UTC\)를 사용 하 여 개체.  
  
## 구문  
  
```  
  
dateObj.getUTCSeconds()   
```  
  
#### 매개 변수  
 필요한 `dateObj` 참조 되는 `Date` 개체입니다.  
  
## 반환 값  
 0에서 59 사이의 정수를 반환 합니다.  시간은 1 초 미만으로 현재 분 이면 0이 반환 됩니다.  경우는 `Date` 시간을 지정 하지 않고 개체 생성, UTC는 기본적으로 초 값은 0입니다.  
  
## 설명  
 로컬 시간으로 초 값을 가져오려면 `getSeconds` 메서드를 사용하십시오.  
  
## 예제  
 다음 예제에서는 `getUTCSeconds` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var date = new Date("1/1/2001");  
document.write(date. getUTCSeconds());  
  
// Output: 0  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용**.[Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getSeconds 메서드\(Date\)](../../javascript/reference/getseconds-method-date-javascript.md)   
 [setSeconds 메서드\(Date\)](../../javascript/reference/setseconds-method-date-javascript.md)   
 [setUTCSeconds 메서드\(Date\)](../../javascript/reference/setutcseconds-method-date-javascript.md)