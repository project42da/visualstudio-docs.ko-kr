---
title: "new 연산자(JavaScript) | Microsoft Docs"
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
  - "new_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "JavaScript의 new 연산자"
ms.assetid: 5ea556ba-7ae6-426c-8430-9032eee5a0a5
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# new 연산자(JavaScript)
새 개체를 만듭니다.  
  
## 구문  
  
```  
new constructor ([arguments])   
```  
  
## 매개 변수  
 `constructor`  
 필수 요소.  개체의 생성자입니다.  생성자에 인수를 사용하지 않는 경우에는 괄호를 생략할 수 있습니다.  
  
 `arguments`  
 선택 사항입니다.  새 개체의 생성자로 전달될 모든 인수입니다.  
  
## 설명  
 `new` 연산자는 다음 작업을 수행합니다.  
  
-   멤버가 없는 개체를 만듭니다.  
  
-   해당 개체에 대해 생성자를 호출하고 `this` 포인터로 새로 만든 개체에 포인터를 전달합니다.  
  
-   그러면 생성자는 생성자에 전달된 인수에 따라 개체를 초기화합니다.  
  
 다음은 **new** 연산자의 새로운 사용 방법에 대한 예입니다.  
  
```javascript  
my_object = new Object;  
my_array = new Array();  
my_date = new Date("Jan 5 1996");  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [function 문](../../javascript/reference/function-statement-javascript.md)