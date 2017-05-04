---
title: "getUTCHours 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getUTCHours"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "시"
  - "UTC 시간, 반환"
  - "getUTCHours 메서드"
ms.assetid: 7c9825dd-4b3a-4614-8e09-f40df123b630
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# getUTCHours 메서드(Date)(JavaScript)
시간 값을 가져옵니다는 `Date` 협정 세계 표준시 \(UTC\)를 사용 하 여 개체.  
  
## 구문  
  
```  
  
dateObj.getUTCHours()   
```  
  
#### 매개 변수  
 필요한 `dateObj` 참조 되는 `Date` 개체입니다.  
  
## 반환 값  
 0과 23 자정 이후로 경과 된 시간을 나타내는 정수를 반환 합니다.  시간 전에 1시: 00 am 인 경우 0이 반환 됩니다.  경우는 `Date` 작성 시간을 지정 하지 않고, 기본적으로는 시간 0 UTC 시간입니다.  이 시간을 0이 아닌 수 제에서.  
  
## 설명  
 로컬 시간을 사용하여 자정부터 경과된 시 값을 가져오려면 `getHours` 메서드를 사용하십시오.  
  
## 예제  
 다음 예제에서는 `getUTCHours` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var date = new Date("1/1/2001");  
document.write(date.getUTCHours());  
document.write("<br/>");  
  
var date2 = new Date("1/1/2001 11:22:33");  
document.write(datee.getUTCHours());  
  
// Output (in the PST time zone):  
// 8  
// 19  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용**.[Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getHours 메서드\(Date\)](../../javascript/reference/gethours-method-date-javascript.md)   
 [setHours 메서드\(Date\)](../../javascript/reference/sethours-method-date-javascript.md)   
 [setUTCHours 메서드\(Date\)](../../javascript/reference/setutchours-method-date-javascript.md)