---
title: "getMilliseconds 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getMilliseconds"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "밀리초"
  - "getMilliseconds 메서드"
ms.assetid: 1b512146-1e8a-44a4-89da-6cc5338d15cb
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# getMilliseconds 메서드(Date)(JavaScript)
로컬 시간을 사용하여 날짜의 밀리초를 가져옵니다.  
  
## 구문  
  
```  
  
dateObj.getMilliseconds()   
```  
  
#### 매개 변수  
 필수 `dateObj` 참조는 `Date` 개체입니다.  
  
## 반환 값  
 날짜의 밀리초를 반환합니다.  값의 범위는 0\-999입니다.  밀리초를 지정하지 않고 날짜가 생성된 경우 반환된 값은 0입니다.  
  
## 설명  
 UTC\(협정 세계 표준시\)에서 밀리초 값을 가져오려면 `getUTCMilliseconds` 메서드를 사용합니다.  
  
## 예제  
 다음 예제에서는 **getMilliseconds** 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var date = new Date("1/1/2001");  
document.write(date.getMilliseconds());  
document.write("<br/>");  
  
date.setMilliseconds(5);  
document.write(date.getMilliseconds());  
// Output:   
// 0  
// 5  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getUTCMilliseconds 메서드\(Date\)](../../javascript/reference/getutcmilliseconds-method-date-javascript.md)   
 [setMilliseconds 메서드\(Date\)](../../javascript/reference/setmilliseconds-method-date-javascript.md)   
 [setUTCMilliseconds 메서드\(Date\)](../../javascript/reference/setutcmilliseconds-method-date-javascript.md)