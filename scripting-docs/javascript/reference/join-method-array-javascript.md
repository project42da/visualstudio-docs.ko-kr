---
title: "join 메서드(Array)(JavaScript) | Microsoft Docs"
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
  - "join"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Join 메서드"
  - "문자열 연결, join 메서드"
  - "배열[Visual Studio], 조인"
ms.assetid: 20f8fde1-014b-488e-9008-464a86e6b21f
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# join 메서드(Array)(JavaScript)
지정된 구분 문자열로 구분되는 배열의 모든 요소를 추가합니다.  
  
## 구문  
  
```  
  
arrayObj.join([separator])   
```  
  
## 매개 변수  
 `arrayObj`  
 필수 요소.  `Array` 개체입니다.  
  
 `separator`  
 선택 사항입니다.  결과 `String`에서 한 배열 요소와 다음 요소를 구분하는 데 사용되는 문자열입니다.  생략하면 배열 요소들은 쉼표로 구분됩니다.  
  
## 설명  
 배열의 요소가 **undefined** 또는 `null`이면 공백 문자열로 처리됩니다.  
  
## 예제  
 다음 예제는 **join** 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var a, b;  
a = new Array(0,1,2,3,4);  
b = a.join("-");  
document.write(b);  
  
// Output:  
// 0-1-2-3-4  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## 참고 항목  
 [String 개체](../../javascript/reference/string-object-javascript.md)