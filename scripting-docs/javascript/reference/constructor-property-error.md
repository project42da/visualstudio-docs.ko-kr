---
title: "constructor 속성(Error) | Microsoft Docs"
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
ms.assetid: 18aea278-2bd5-457b-83a5-d8d8f1226e0c
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# constructor 속성(Error)
오류를 만드는 함수를 지정합니다.  
  
## 구문  
  
```  
  
error.constructor  
```  
  
## 설명  
 필수 `error`는 error 개체의 이름입니다.  
  
 `constructor` 속성은 초기 설정을 가지는 모든 초기 설정 개체의 멤버입니다.  `constructor` 속성은 특정 개체의 인스턴스를 구성하는 함수에 대한 참조를 포함합니다.  
  
## 예제  
 다음 예제에서는 constructor 속성을 사용하는 방법을 보여 줍니다.  
  
```javascript  
var x = new Error("This is an error");  
  
if (x.constructor == Error)  
    document.write("Object is an error.");  
  
// Output:  
// Object is an error.  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]