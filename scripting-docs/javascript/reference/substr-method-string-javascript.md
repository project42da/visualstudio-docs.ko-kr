---
title: "substr 메서드(String)(JavaScript) | Microsoft Docs"
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
  - "substr"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "substr 메서드"
ms.assetid: f12541c1-2623-482e-941d-2e22bc3c4a4a
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# substr 메서드(String)(JavaScript)
지정한 위치에서 시작하고 지정한 길이인 부분 문자열을 가져옵니다.  
  
## 구문  
  
```  
  
stringvar.substr(start [, length ])   
```  
  
## 매개 변수  
 `stringvar`  
 필수 요소.  부분 문자열이 추출되는 `String` 개체 또는 문자열 리터럴입니다.  
  
 `start`  
 필수 요소.  원하는 부분 문자열의 시작 위치입니다.  문자열에서 첫 번째 문자의 인덱스는 0입니다.  
  
 `length`  
 선택 사항입니다.  반환된 부분 문자열에 포함할 문자 수입니다.  
  
## 설명  
 `length`가 0 또는 음수이면 빈 문자열이 반환됩니다.  length를 지정하지 않으면 `stringvar`이 끝날 때까지 부분 문자열이 계속됩니다.  
  
## 예제  
 다음 예제에서는 `substr` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var s = "The quick brown fox jumps over the lazy dog.";  
var ss = s.substr(10, 5);    
document.write("[" + ss + "] <br>");  
  
ss = s.substr(10);  
document.write("[" + ss + "] <br>");  
  
ss = s.substr(10, -5);  
document.write("[" + ss + "] <br>");  
  
// Output:  
// [brown]   
// [brown fox jumps over the lazy dog.]   
// []  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [String 개체](../../javascript/reference/string-object-javascript.md)  
  
## 참고 항목  
 [substring 메서드\(String\)](../../javascript/reference/substring-method-string-javascript.md)