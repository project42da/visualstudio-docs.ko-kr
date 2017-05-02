---
title: "valueOf 메서드(Date) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 39a1f96e-14b0-4db2-b53d-cdfd67cbb208
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# valueOf 메서드(Date)
UTC 1970년 1월 1일 자정부터 밀리초 단위로 저장된 시간 값을 반환합니다.  
  
## 구문  
  
```  
  
date.valueOf()  
```  
  
#### 매개 변수  
 `date` 개체는 임의의 Date 인스턴스입니다.  
  
## 반환 값  
 UTC 1970년 1월 1일 자정부터 밀리초 단위로 저장된 시간 값입니다.  이 값은 `getTime`과 동일한 값입니다.  
  
## 예제  
 다음 예제에서는 `valueOf` 메서드 및 날짜를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var myDate = new Date();  
myDate.setFullYear(2100, 5, 5);  
if (myDate.getTime() == myDate.valueOf())  
    document.write("values are the same");  
else  
    document.write("values are different");  
  
// Output: values are the same  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]