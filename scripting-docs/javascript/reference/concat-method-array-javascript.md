---
title: "concat 메서드(Array)(JavaScript) | Microsoft Docs"
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
  - "concat"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "concat 메서드(array)"
  - "Concat 메서드"
ms.assetid: bc2b4a6a-209e-4d59-8c24-59db01d53b1e
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# concat 메서드(Array)(JavaScript)
둘 이상의 배열을 결합합니다.  
  
## 구문  
  
```  
  
array1.concat([item1[, item2[, . . . [, itemN]]]])   
```  
  
## 매개 변수  
 `array1`  
 필수 요소.  다른 배열을 연결할 `Array` 개체입니다.  
  
 `item1,. . ., itemN`  
 선택 사항입니다.  `array1`의 끝에 추가할 항목입니다.  
  
## 설명  
 `concat` 메서드는 `array1`과 주어진 다른 항목 간의 연결을 포함하는 `Array` 개체를 반환합니다.  
  
 배열에 추가될 항목\(*item1 itemN*\)은 목록의 첫 번째 항목부터 순서대로 추가됩니다.  항목 중 하나가 배열이면 그 내용이 `array1`의 끝에 추가됩니다.  항목이 배열이 아니면 배열의 끝에 단일 배열 요소로 추가됩니다.  
  
 소스 배열의 요소는 결과로 나오는 배열에 다음 방식으로 복사됩니다.  
  
-   개체가 새 배열에 연결될 임의의 배열에서 복사되는 경우 개체 참조는 계속해서 같은 개체를 가리킵니다.  새 배열 또는 원래 배열의 변경 내용은 나머지 배열에 영향을 줍니다.  
  
-   숫자 또는 문자열 값이 새 배열에 추가되는 경우 값만 복사됩니다.  한 배열의 값을 변경해도 다른 배열의 값에는 영향을 주지 않습니다.  
  
## 예제  
 다음 예제에서는 배열과 함께 사용될 때 `concat` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var a, b, c, d;  
a = new Array(1,2,3);  
b = "dog";  
c = new Array(42, "cat");  
d = a.concat(b, c);  
document.write(d);  
  
//Output:   
1, 2, 3, "dog", 42, "cat"  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## 참고 항목  
 [concat 메서드\(String\)](../../javascript/reference/concat-method-string-javascript.md)   
 [join 메서드\(Array\)](../../javascript/reference/join-method-array-javascript.md)