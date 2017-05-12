---
title: "toString 메서드(Date) | Microsoft Docs"
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
ms.assetid: d3037289-d805-409b-8781-045c59a2c404
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# toString 메서드(Date)
날짜를 나타내는 문자열을 반환합니다.  문자열의 형식은 로캘에 따라 달라집니다.  미국 영어\(en\-us\)의 경우 다음과 같습니다.  
  
 *요일* *월* *일* *시간*: *분*:*초* *시간대* *년*  
  
## 구문  
  
```  
  
date.toString()  
```  
  
## 매개 변수  
 `date`  
 필수 요소.  문자열로 나타낼 날짜입니다.  
  
## 반환 값  
 날짜의 문자열 표현을 반환합니다.  
  
## 예제  
 다음 예제에서는 `toString` 메서드 및 날짜를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var myDate = new Date();  
myDate.setFullYear(2100, 5, 5);  
var dateString = myDate.toString();  
document.write(dateString);  
  
// Output: <date>  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]