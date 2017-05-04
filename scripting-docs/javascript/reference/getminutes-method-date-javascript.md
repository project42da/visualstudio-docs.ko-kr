---
title: "getMinutes 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getMinutes"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "GetMinutes 메서드"
  - "minutes 메서드"
ms.assetid: d4139b5d-04e1-474c-9a83-e9d40597243a
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# getMinutes 메서드(Date)(JavaScript)
로컬 시간을 사용하여 `Date` 개체의 분을 가져옵니다.  
  
## 구문  
  
```  
  
dateObj.getMinutes()   
```  
  
#### 매개 변수  
 필수 `dateObj` 참조는 `Date` 개체입니다.  
  
## 반환 값  
 0에서 59 사이의 정수를 반환합니다.  시간이 현재 시에서 1초가 지나지 않았으면 0이 반환됩니다.  시간을 지정하지 않고 `Date` 개체를 만든 경우 기본적으로 분 값은 0입니다.  
  
## 설명  
 UTC\(협정 세계 표준시\)를 사용하여 분 값을 가져오려면 `getUTCMinutes` 메서드를 사용합니다.  
  
## 예제  
 다음 예제에서는 `getMinutes` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var date = new Date("1/1/2001");  
document.write(date.getMinutes());  
document.write("<br/>");  
  
date.setMinutes(5);  
document.write(date.getMinutes());  
  
// Output:  
// 0  
// 5  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getUTCMinutes 메서드\(Date\)](../../javascript/reference/getutcminutes-method-date-javascript.md)   
 [setMinutes 메서드\(Date\)](../../javascript/reference/setminutes-method-date-javascript.md)   
 [setUTCMinutes 메서드\(Date\)](../../javascript/reference/setutcminutes-method-date-javascript.md)