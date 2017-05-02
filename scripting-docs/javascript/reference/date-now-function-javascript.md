---
title: "Date.now 함수(JavaScript) | Microsoft Docs"
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
  - "now 메서드"
ms.assetid: 41beda89-1a40-4fb1-88b0-38c090af739b
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# Date.now 함수(JavaScript)
현재 날짜와 시간을 가져옵니다.  
  
## 구문  
  
```  
  
Date.now()  
```  
  
## 반환 값  
 1970년 1월 1일 자정과 현재 날짜 및 시간 사이의 밀리초 값입니다.  
  
## 설명  
 [getTime 메서드](../../javascript/reference/gettime-method-date-javascript.md)는 1970년 1월 1일과 지정된 날짜 사이의 밀리초 값을 반환합니다.  
  
 경과된 시간을 계산하고 날짜를 비교하는 방법에 대한 자세한 내용은 [날짜 및 시간 계산\(JavaScript\)](../../javascript/calculating-dates-and-times-javascript.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 `now` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var start = Date.now();  
var response = prompt("What is your name?", "");  
var end = Date.now();  
var elapsed = (end - start) / 1000;  
document.write("You took " + elapsed + " seconds" + " to type: " + response);  
  
// Output:  
// You took <seconds> seconds to type: <name>  
```  
  
## 요구 사항  
 Internet Explorer 9 이전의 설치된 버전에서는 지원되지 않습니다.  그러나 Quirks, Internet Explorer 6 표준, Internet Explorer 7 표준, Internet Explorer 8 표준, Internet Explorer 9 표준 및 Internet Explorer 10 표준의 문서 모드에서 지원됩니다.  [!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱에서도 지원됩니다.  
  
## 참고 항목  
 [getTime 메서드\(Date\)](../../javascript/reference/gettime-method-date-javascript.md)   
 [Date 개체](../../javascript/reference/date-object-javascript.md)   
 [날짜 및 시간 계산\(JavaScript\)](../../javascript/calculating-dates-and-times-javascript.md)   
 [JavaScript 메서드](../../javascript/reference/javascript-methods.md)