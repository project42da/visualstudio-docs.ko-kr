---
title: "length 속성(Function)(JavaScript) | Microsoft Docs"
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
  - "length Property"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Length 속성"
  - "length 속성(function)"
ms.assetid: fdc8e1c9-0dac-4e1b-ba3a-11073c37ef63
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# length 속성(Function)(JavaScript)
함수에 정의된 인수 개수를 가져옵니다.  
  
## 구문  
  
```  
  
functionName.length  
```  
  
## 설명  
 필수 *functionName*은 함수의 이름입니다.  
  
 함수의 **length** 속성은 함수 인스턴스를 만들 때 스크립팅 엔진에 의해 함수 정의에 있는 인수 개수로 초기화됩니다.  
  
 함수의 **length** 속성 값과 다른 인수 개수로 함수를 호출하면 함수에 따라 그 결과가 달라집니다.  
  
## 예제  
 다음 예제에서는 **length** 속성의 사용법을 보여 줍니다.  
  
```javascript  
function ArgTest(a, b){  
    var s = "";  
  
    s += "Expected Arguments: " + ArgTest.length;  
    s += "<br />";  
    s += "Passed Arguments: " + arguments.length;  
  
    return s;  
}  
  
document.write(ArgTest(1, 2));  
  
// Output:   
// Expected Arguments: 2  
// Passed Arguments: 2  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## 참고 항목  
 [arguments 속성\(Function\)](../../javascript/reference/arguments-property-function-javascript.md)   
 [length 속성\(Array\)](../../javascript/reference/length-property-array-javascript.md)   
 [length 속성\(String\)](../../javascript/reference/length-property-string-javascript.md)