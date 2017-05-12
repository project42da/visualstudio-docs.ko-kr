---
title: "callee 속성(arguments)(JavaScript) | Microsoft Docs"
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
  - "callee"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "callee 속성"
ms.assetid: ad9d4d21-73f0-44f6-8bec-502f3456cd23
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# callee 속성(arguments)(JavaScript)
지정된 `Function` 개체의 본문에 해당하는 실행 중인 `Function` 개체를 반환합니다.  
  
## 구문  
  
```  
[function.]arguments.callee  
```  
  
## 설명  
 선택적인 *function* 인수는 현재 실행 중인 `Function` 개체의 이름입니다.  
  
 `callee` 속성은 관련된 함수가 실행될 때만 사용 가능한 **arguments** 개체의 멤버입니다.  
  
 `callee` 속성의 초기 값은 실행 중인 `Function` 개체입니다.  이 속성은 익명 함수의 재귀를 허용합니다.  
  
## 예제  
  
```javascript  
function factorial(n){  
  if (n <= 0)  
     return 1;  
  else  
     return n * arguments.callee(n - 1)  
}  
document.write(factorial(4));  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [arguments 개체](../../javascript/reference/arguments-object-javascript.md)&#124; [Function 개체](../../javascript/reference/function-object-javascript.md)  
  
## 참고 항목  
 [caller 속성\(Function\)](../../javascript/reference/caller-property-function-javascript.md)