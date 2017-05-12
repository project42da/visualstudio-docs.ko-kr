---
title: "getFullYear 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getFullYear"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "날짜, 연도 반환"
  - "Date 개체"
  - "getFullYear 메서드"
ms.assetid: f9ec1262-02e9-4791-90b5-48f33b1dc4bc
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# getFullYear 메서드(Date)(JavaScript)
로컬 시간을 사용하여 연도를 가져옵니다.  
  
## 구문  
  
```  
  
dateObj.getFullYear()   
```  
  
#### 매개 변수  
 필수 `dateObj` 참조는 `Date` 개체입니다.  
  
## 반환 값  
 네 자리 숫자로 된 연도입니다.  예를 들어 1976년은 1976으로 반환됩니다.  `Date` 생성자 또는 `setFullYear`에서 두 자리로 지정된 연도는 20세기에 있는 것으로 간주되므로 "5\/14\/12"의 경우 `getFullYear`는 "1912"를 반환합니다.  
  
## 설명  
 UTC\(협정 세계 표준시\)를 사용하여 연도 값을 가져오려면 `getUTCFullYear` 메서드를 사용하세요.  
  
## 예제  
 다음 예제에서는 **getFullYear** 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var date = new Date("1/1/01");  
document.write(date.getFullYear());  
  
// Output: 1901  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getUTCFullYear 메서드\(Date\)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [setFullYear 메서드\(Date\)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setUTCFullYear 메서드\(Date\)](../../javascript/reference/setutcfullyear-method-date-javascript.md)