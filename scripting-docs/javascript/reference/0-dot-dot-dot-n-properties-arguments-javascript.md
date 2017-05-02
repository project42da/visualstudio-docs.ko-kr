---
title: "0...n 속성(arguments)(JavaScript) | Microsoft Docs"
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
  - "0...n"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "0...n 속성"
ms.assetid: 52857c4b-3d56-4500-93ff-4db4729c2578
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# 0...n 속성(arguments)(JavaScript)
실행 함수의 **arguments** 속성에 의해 반환되는 **arguments** 개체에서 각 인수의 실제 값을 반환합니다.  
  
## 구문  
  
```  
[function.]arguments[[0|1|2|...|n]]  
```  
  
## 매개 변수  
 *function*  
 선택 사항입니다.  현재 실행 중인 `Function` 개체의 이름입니다.  
  
 0, 1, 2, *, n*  
 필수 요소.  0에서 *n*까지의 음수가 아닌 정수로, 여기서 0은 첫 번째 인수를 나타내고 *n*은 마지막 인수를 나타냅니다.  최종 인수 *n*의 값은 **arguments.length\-1**입니다.  
  
## 설명  
 0 .  .  .  n 속성에 의해 반환되는 값은 실행 함수로 전달되는 실제 값입니다.  실제로 인수의 배열은 아니지만 **arguments** 개체를 구성하는 각 인수는 배열 요소에 액세스하는 것과 같은 방법으로 액세스됩니다.  
  
## 예제  
 다음 예제에서는 **0 . . .**  ***n*** 속성\(**arguments** 개체\)을 사용하는 방법을 보여 줍니다.  예제를 올바르게 이해하기 위해서는 함수에 인수를 한 개 이상 전달해보십시오.  
  
```javascript  
function ArgTest(){  
   var s = "";  
   s += "The individual arguments are: "  
   for (n = 0; n < arguments.length; n++){  
      s += ArgTest.arguments[n];  
      s += " ";  
   }  
   return(s);  
}  
document.write(ArgTest(1, 2, "hello", new Date()));  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [arguments 개체](../../javascript/reference/arguments-object-javascript.md)&#124; [Function 개체](../../javascript/reference/function-object-javascript.md)  
  
## 참고 항목  
 [length 속성\(arguments\)](../../javascript/reference/length-property-arguments-javascript.md)   
 [length 속성\(Function\)](../../javascript/reference/length-property-function-javascript.md)