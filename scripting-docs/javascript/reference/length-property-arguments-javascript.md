---
title: "length 속성(arguments)(JavaScript) | Microsoft Docs"
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
  - "length 속성(arguments)"
ms.assetid: 3cf36823-15bc-489b-a951-24c4923d9dba
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# length 속성(arguments)(JavaScript)
호출자에 의해 함수에 전달되는 인수의 실제 개수를 반환합니다.  
  
## 구문  
  
```  
[function.]arguments.length  
```  
  
## 설명  
 선택적인 *function* 인수는 현재 실행 중인 `Function` 개체의 이름입니다.  
  
 **arguments** 개체의 **length** 속성은 해당 함수에서 실행이 시작되었을 때 `Function` 개체에 전달되는 인수의 실제 개수로 스크립팅 엔진에 의해 초기화됩니다.  
  
## 예제  
 다음 예제는 **arguments**  개체의  **length** 속성의 사용법을 보여 줍니다.  예제를 올바르게 이해하기 위해서는 필요한 2개의 인수 대신 더 많은 인수를 함수에 전달해보십시오.  
  
```javascript  
function ArgTest(a, b){  
   var s = "";  
  
   s += "Expected Arguments: " + ArgTest.length;  
   s += "<br />";  
   s += "Passed Arguments: " + arguments.length;  
  
   document.write (s);  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [arguments 개체](../../javascript/reference/arguments-object-javascript.md)&#124; [Function 개체](../../javascript/reference/function-object-javascript.md)  
  
## 참고 항목  
 [arguments 속성\(Function\)](../../javascript/reference/arguments-property-function-javascript.md)   
 [length 속성\(Array\)](../../javascript/reference/length-property-array-javascript.md)   
 [length 속성\(String\)](../../javascript/reference/length-property-string-javascript.md)