---
title: "getSeconds 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getSeconds"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "seconds 메서드"
  - "GetSeconds 메서드"
ms.assetid: 97b10674-af0b-4681-a846-38f972196501
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# getSeconds 메서드(Date)(JavaScript)
초를 가져옵니다는 `Date` 개체, 현지 시간을 사용 합니다.  
  
## 구문  
  
```  
  
dateObj.getSeconds()   
```  
  
#### 매개 변수  
 필요한 `dateObj` 참조 되는 `Date` 개체입니다.  
  
## 반환 값  
 0에서 59 사이의 정수를 반환 합니다.  시간은 1 초 미만으로 현재 분 이면 0이 반환 됩니다.  경우는 `Date` 작성 시간을 지정 하지 않고, 기본적으로 초 값은 0입니다.  
  
## 설명  
 협정 세계 표준시 \(UTC\)를 사용 하 여 값의 초를 얻을 수 있는 `getUTCSeconds` 메서드.  
  
## 예제  
 다음 예제에서는 `getSeconds` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var date = new Date("1/1/2001");  
document.write(date.getSeconds());  
document.write("<br/>");  
  
date.setSeconds(5);  
document.write(date.getSeconds());  
  
// Output:  
// 0  
// 5  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용**.[Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getUTCSeconds 메서드\(Date\)](../../javascript/reference/getutcseconds-method-date-javascript.md)   
 [setSeconds 메서드\(Date\)](../../javascript/reference/setseconds-method-date-javascript.md)   
 [setUTCSeconds 메서드\(Date\)](../../javascript/reference/setutcseconds-method-date-javascript.md)