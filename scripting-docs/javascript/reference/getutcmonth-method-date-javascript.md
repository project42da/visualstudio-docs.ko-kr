---
title: "getUTCMonth 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getUTCMonth"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "날짜, UTC"
  - "UTC 날짜, 반환"
  - "Month 메서드"
  - "getUTCMonth 메서드"
ms.assetid: eabae139-4da0-4e4a-a4cb-608e6375fc9e
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# getUTCMonth 메서드(Date)(JavaScript)
이달의 가져옵니다는 `Date` 협정 세계 표준시 \(UTC\)를 사용 하 여 개체.  
  
## 구문  
  
```  
  
dateObj.getUTCMonth()   
```  
  
#### 매개 변수  
 필요한 `dateObj` 참조 되는 `Date` 개체입니다.  
  
## 반환 값  
 0 \(1 월\)과 11 \(12 월\) 사이의 정수를 반환 합니다.  
  
## 설명  
 로컬 시간으로 월 값을 가져오려면 **getMonth** 메서드를 사용하십시오.  
  
## 예제  
 다음 예제에서는 `getUTCMonth` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var date = new Date("2/2/2002");  
document.write(date.getUTCMonth());  
  
// Output: 1  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용**.[Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getMonth 메서드\(Date\)](../../javascript/reference/getmonth-method-date-javascript.md)   
 [setMonth 메서드\(Date\)](../../javascript/reference/setmonth-method-date-javascript.md)   
 [setUTCMonth 메서드\(Date\)](../../javascript/reference/setutcmonth-method-date-javascript.md)