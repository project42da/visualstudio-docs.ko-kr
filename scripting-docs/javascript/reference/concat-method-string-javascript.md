---
title: "concat 메서드(String)(JavaScript) | Microsoft Docs"
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
  - "concat 메서드(String)"
  - "Concat 메서드"
ms.assetid: 5d28ebb2-d534-4179-9297-a4c821ee9f24
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# concat 메서드(String)(JavaScript)
둘 이상의 문자열의 연결을 포함하는 문자열을 반환합니다.  
  
## 구문  
  
```  
  
string1. concat([string2[, string3[, . . . [, stringN]]]])  
```  
  
## 매개 변수  
 `string1`  
 필수 요소.  지정된 다른 모든 문자열을 연결할 `String` 개체 또는 문자열 리터럴입니다.  
  
 `string2,. . ., stringN`  
 선택 사항입니다.  `string1`의 끝에 추가할 문자열입니다.  
  
## 설명  
 `concat` 메서드의 결과는 `result` \= `string1` \+ `string2` \+ `string3` \+ `stringN`과 같습니다.  소스 문자열이나 결과로 나오는 문자열의 내용을 변경해도 다른 문자열에는 영향을 주지 않습니다.  인수가 문자열이 아닌 경우 먼저 문자열로 변환한 다음 `string1`에 연결합니다.  
  
## 예제  
 다음 예제는 문자열을 사용한 `concat` 메서드의 사용 예를 보여 줍니다.  
  
```javascript  
var str1 = "ABCD"  
var str2 = "EFGH";  
var str3 = "1234";  
var str4 = "5678";  
document.write(str1.concat(str2, str3, str4));  
  
// Output: "ABCDEFGH12345678"  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [String 개체](../../javascript/reference/string-object-javascript.md)  
  
## 참고 항목  
 [더하기 연산자\(\+\)](../../javascript/reference/addition-operator-decrement-javascript.md)