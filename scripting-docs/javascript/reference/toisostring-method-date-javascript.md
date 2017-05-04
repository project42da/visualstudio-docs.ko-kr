---
title: "toISOString 메서드(Date)(JavaScript) | Microsoft Docs"
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
helpviewer_keywords: 
  - "toISOString 메서드[JavaScript]"
ms.assetid: 58577d8f-3ae8-4887-8687-26233ea79ff6
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# toISOString 메서드(Date)(JavaScript)
날짜를 ISO 형식의 문자열 값으로 반환합니다.  
  
## 구문  
  
```javascript  
  
objDate.toISOString()  
```  
  
## 반환 값  
 ISO\(International Organization for Standardization\) 형식의 날짜에 대한 문자열 표현입니다.  
  
## 예외  
 `objDate`에 올바른 날짜가 포함되지 않을 경우 `RangeError` 예외가 throw됩니다.  
  
## 설명  
 ISO 형식은 ISO 8601 형식의 간소화된 버전입니다.  자세한 내용은 [날짜 및 시간 문자열](../../javascript/date-and-time-strings-javascript.md)을 참조하세요.  
  
 시간대는 항상 UTC이며 출력에서 접미사 Z로 표시됩니다.  
  
## 예제  
 다음 예제에서는 `toISOString` 메서드의 사용법을 보여 줍니다.  
  
```javascript  
var dt = new Date("30 July 2010 15:05 UTC");  
document.write(dt.toISOString());  
document.write("<br />");  
document.write(dt.toUTCString());  
  
// Output:  
//  2010-07-30T15:05:00.000Z  
//  Fri, 30 Jul 2010 15:05:00 UTC  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## 참고 항목  
 [Date 개체](../../javascript/reference/date-object-javascript.md)   
 [날짜 및 시간 문자열](../../javascript/date-and-time-strings-javascript.md)