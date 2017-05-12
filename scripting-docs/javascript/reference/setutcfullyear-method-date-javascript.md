---
title: "setUTCFullYear 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "setUTCFullYear"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "날짜, UTC"
  - "setUTCFullYear 메서드"
  - "UTC 날짜, 설정"
ms.assetid: e6c51b49-0149-4f9a-aa74-c73c0306f98e
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# setUTCFullYear 메서드(Date)(JavaScript)
UTC\(협정 세계 표준시\)를 사용하여 `Date` 개체의 연도 값을 설정합니다.  
  
## 구문  
  
```  
  
dateObj.setUTCFullYear(numYear[, numMonth[, numDate]])   
```  
  
## 매개 변수  
 `dateObj`  
 필수 요소.  임의의 `Date` 개체입니다.  
  
 `numYear`  
 필수 요소.  연도에 해당하는 숫자 값입니다.  
  
 `numMonth`  
 선택 사항입니다.  월에 해당하는 숫자 값입니다.  1월의 값은 0이고 다른 달 값은 순차적으로 증가합니다.  *numDate*를 사용하면 반드시 사용해야 합니다.  
  
 *numDate*  
 선택 사항입니다.  일\(한 달 기준\)에 해당하는 숫자 값입니다.  
  
## 설명  
 선택적 인수를 지정하지 않으면 선택적 인수를 갖는 모든 **set** 메서드는 해당 **get** 메서드에서 반환된 값을 사용합니다.  예를 들어 `numMonth` 인수를 지정하지 않은 경우 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]는 `getUTCMonth` 메서드에서 반환된 값을 사용합니다.  
  
 또한 인수 값이 범위를 초과하거나 음수이면 이에 따라 저장된 다른 값들도 수정됩니다.  
  
 현지 시간을 사용하는 연도 값을 설정하려면 `setFullYear` 메서드를 사용하세요.  
  
 `Date` 개체가 지원하는 연도 범위는 1970년을 전후로 약 285,616년까지입니다.  
  
## 예제  
 다음 예제에서는 `setUTCFullYear` 메서드의 사용법을 보여 줍니다.  
  
```javascript  
var dtFirst = new Date();  
dtFirst.setUTCFullYear(2007);  
  
var dtSecond = new Date();  
// 10 is the value for November.   
dtSecond.setUTCFullYear(2008, 10, 3);   
  
document.write (dtFirst.toUTCString());  
document.write ("<br />");  
document.write (dtSecond.toUTCString());  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getFullYear 메서드\(Date\)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [getUTCFullYear 메서드\(Date\)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [setFullYear 메서드\(Date\)](../../javascript/reference/setfullyear-method-date-javascript.md)