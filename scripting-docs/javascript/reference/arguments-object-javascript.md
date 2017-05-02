---
title: "arguments 개체(JavaScript) | Microsoft Docs"
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
  - "arguments"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "arguments 개체"
  - "인수, arguments 개체"
ms.assetid: 5eb79ca9-bbb8-4a42-aaf5-16a93ecb425f
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# arguments 개체(JavaScript)
현재 실행 중인 함수 및 이 함수를 호출한 함수에 대한 인수를 나타내는 개체입니다.  
  
## 구문  
  
```  
[function.]arguments[n]  
```  
  
## 매개 변수  
 *함수*  
 선택 사항입니다.  현재 실행 중인 `Function` 개체의 이름입니다.  
  
 *n*  
 필수 요소.  `Function` 개체에 전달되는 인수 값에 대한 인덱스\(0부터 시작\)입니다.  
  
## 설명  
 **arguments** 개체는 명시적으로 만들 수 없습니다.  **arguments** 개체는 함수가 실행을 시작할 때만 사용할 수 있습니다.  함수의 **arguments** 개체는 배열이 아니지만 배열 요소에 액세스하는 방식과 동일하게 각각의 인수에 액세스할 수 있습니다.  *n* 인덱스는 실제로 **arguments** 개체의 **0** ***n*** 속성 중 하나에 대한 참조입니다.  
  
## 예제  
 다음 예제에서는 **arguments** 개체의 사용법을 보여 줍니다.  
  
```javascript  
function ArgTest(a, b)  
{  
   var s = "";  
  
   s += "Expected Arguments: " + ArgTest.length;  
   s += "<br />";  
   s += "Passed Arguments: " + arguments.length;  
   s += "<br />";  
  
   s += "The individual arguments are: "  
   for (n = 0; n < arguments.length; n++)  
   {  
      s += ArgTest.arguments[n];  
      s += " ";  
   }  
  
   document.write(s);  
}  
  
ArgTest(1, 2, "hello", new Date())  
  
// Output:  
// Expected Arguments: 2  
// Passed Arguments: 4  
// The individual arguments are: 1 2 hello Tues Jan 8 08:27:09 PST 20xx  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [0...n 속성\(arguments\)](../../javascript/reference/0-dot-dot-dot-n-properties-arguments-javascript.md)   
 [callee 속성\(arguments\)](../../javascript/reference/callee-property-arguments-javascript.md)   
 [length 속성\(arguments\)](../../javascript/reference/length-property-arguments-javascript.md)