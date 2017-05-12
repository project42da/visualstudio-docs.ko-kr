---
title: "arguments 속성(Function)(JavaScript) | Microsoft Docs"
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
  - "인수, 인수 속성"
  - "Arguments 속성"
ms.assetid: efc7a1ee-0880-4f05-b0f2-808f31a4af1d
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# arguments 속성(Function)(JavaScript)
현재 실행 중인 `Function` 개체의 인수를 가져옵니다.  
  
## 구문  
  
```  
  
function.arguments  
```  
  
## 설명  
 `function` 인수는 현재 실행 중인 함수의 이름이며 생략할 수 있습니다.  
  
 이 속성을 사용하면 함수에서 다양한 수의 인수를 처리할 수 있습니다.  `arguments` 개체의 **length** 속성은 함수로 전달되는 인수의 수를 포함합니다.  `arguments` 개체에 포함된 각 인수는 배열 요소에 액세스하는 방법과 같은 방법으로 액세스할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `arguments` 속성의 사용 예를 보여 줍니다.  
  
```javascript  
function ArgTest(arg1, arg2){  
   var s = "";  
   s += "The individual arguments are: "  
   for (n = 0; n < arguments.length; n++){  
      s += ArgTest.arguments[n];  
      s += " ";  
   }  
   return(s);  
}  
document.write(ArgTest(1, 2, "hello"));  
  
//Output: function ArgTest(arg1, arg2){  
   var s = "";  
   s += "The individual arguments are: "  
   for (n = 0; n < arguments.length; n++){  
      s += ArgTest.arguments[n];  
      s += " ";  
   }  
   return(s);  
}  
document.write(ArgTest(1, 2, "hello"));  
  
// Output: The individual arguments are: 1 2 hello  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## 참고 항목  
 [arguments 개체](../../javascript/reference/arguments-object-javascript.md)   
 [function 문](../../javascript/reference/function-statement-javascript.md)