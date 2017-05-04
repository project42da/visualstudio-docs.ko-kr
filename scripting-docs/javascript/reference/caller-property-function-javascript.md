---
title: "caller 속성(Function)(JavaScript) | Microsoft Docs"
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
  - "caller"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "caller 속성"
  - "함수 호출, 실행 중인 함수"
ms.assetid: ae210853-7160-4102-9cfd-ab489f180ce1
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# caller 속성(Function)(JavaScript)
현재 함수를 호출한 함수를 가져옵니다.  
  
## 구문  
  
```  
  
functionName.caller  
```  
  
## 설명  
 `functionName` 개체는 임의의 실행 함수 이름입니다.  
  
 `caller` 속성은 함수가 실행 중인 경우에만 해당 함수에 대해 정의됩니다.  [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 프로그램의 맨 위 수준에서 함수를 호출하면 `caller`는 `null`을 포함합니다.  
  
 `caller` 속성을 문자열 컨텍스트에 사용하면 `functionName`.`toString`과 같은 결과가 나옵니다. 즉, 함수의 역컴파일된 텍스트가 표시됩니다.  
  
 다음 예제에서는 `caller` 속성의 사용 예를 보여 줍니다.  
  
```javascript  
function CallLevel(){  
   if (CallLevel.caller == null)  
      return("CallLevel was called from the top level.");  
   else  
      return("CallLevel was called by another function.");  
}  
  
document.write(CallLevel());  
  
// Output: CallLevel was called from the top level.  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## 참고 항목  
 [function 문](../../javascript/reference/function-statement-javascript.md)