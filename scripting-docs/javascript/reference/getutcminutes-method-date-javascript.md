---
title: "getUTCMinutes 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getUTCMinutes"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "분"
  - "UTC 시간, 반환"
  - "getUTCMinutes 메서드"
ms.assetid: b6d92543-b285-4e46-8f47-bba36e53fabd
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# getUTCMinutes 메서드(Date)(JavaScript)
분을 가져옵니다는 `Date` 협정 세계 표준시 \(UTC\)를 사용 하 여 개체.  
  
## 구문  
  
```  
  
dateObj.getUTCMinutes()   
```  
  
#### 매개 변수  
 필요한 `dateObj` 참조 되는 `Date` 개체입니다.  
  
## 반환 값  
 0에서 59 사이의 정수를 반환 합니다.  시간 1 분 정각입니다 0이 반환 됩니다.  경우는 `Date` 작성 시간을 지정 하지 않고, 기본 UTC 분 값은 0입니다.  그러나 다른 시간대에서 달라질 수 있습니다.  
  
## 설명  
 로컬 시간을 사용하여 저장된 분 값을 가져오려면 `getMinutes` 메서드를 사용하십시오.  
  
## 예제  
 다음 예제에서는 `getUTCMinutes` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var date = new Date("1/1/2001");  
document.write(date.getUTCMinutes());  
document.write("<br/>");  
  
date.setMinutes(5);  
document.write(date.getUTCMinutes());  
  
// Output:   
// 0  
// 5  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용**.[Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getMinutes 메서드\(Date\)](../../javascript/reference/getminutes-method-date-javascript.md)   
 [setMinutes 메서드\(Date\)](../../javascript/reference/setminutes-method-date-javascript.md)   
 [setUTCMinutes 메서드\(Date\)](../../javascript/reference/setutcminutes-method-date-javascript.md)