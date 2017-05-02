---
title: "getUTCMilliseconds 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getUTCMilliseconds"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "밀리초"
  - "UTC 시간, 반환"
  - "getUTCMilliseconds 메서드"
ms.assetid: 7491d387-7b6a-40df-89e5-55c64795ef70
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# getUTCMilliseconds 메서드(Date)(JavaScript)
밀리초 단위로 가져옵니다는 `Date` 협정 세계 표준시 \(UTC\)를 사용 하 여 개체.  
  
## 구문  
  
```  
  
dateObj.getUTCMilliseconds()   
```  
  
#### 매개 변수  
 필요한 `dateObj` 참조 되는 `Date` 개체입니다.  
  
## 반환 값  
 밀리초 값의 범위는 0\-999를 반환 합니다.  
  
## 설명  
 현지 시간에서 밀리초를 얻을 수 있는 `getMilliseconds` 메서드.  
  
## 예제  
 다음 예제에서는 `getUTCMilliseconds` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var date = new Date("1/1/2001");  
document.write(date.getUTCMilliseconds());  
document.write("<br/>");  
  
date.setMilliseconds(34);  
document.writedate.getUTCMilliseconds());  
  
// Output:  
// 0   
// 34   
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용**.[Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getMilliseconds 메서드\(Date\)](../../javascript/reference/getmilliseconds-method-date-javascript.md)   
 [setMilliseconds 메서드\(Date\)](../../javascript/reference/setmilliseconds-method-date-javascript.md)   
 [setUTCMilliseconds 메서드\(Date\)](../../javascript/reference/setutcmilliseconds-method-date-javascript.md)