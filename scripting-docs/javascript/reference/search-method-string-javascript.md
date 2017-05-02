---
title: "search 메서드(String)(JavaScript) | Microsoft Docs"
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
  - "search"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "search 메서드"
ms.assetid: 1cae0fbc-3319-4327-ba4e-d5fa2c4a9ba0
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# search 메서드(String)(JavaScript)
정규식 검색에서 첫 번째로 일치하는 부분 문자열을 찾습니다.  
  
## 구문  
  
```  
  
stringObj.search(rgExp)   
```  
  
## 매개 변수  
 `stringObj`  
 필수 요소.  검색을 수행할 `String` 개체 또는 문자열 리터럴입니다.  
  
 `rgExp`  
 필수 요소.  정규식 패턴 및 적용 가능한 플래그를 포함하는 **Regular Expression** 개체의 인스턴스입니다.  
  
## 반환 값  
 일치하는 부분이 있으면, **search** 메서드가 처음으로 일치하는 문자열의 시작 부분에서 오프셋을 나타내는 정수 값을 반환합니다.  일치하는 부분이 없으면 \-1을 반환합니다.  
  
## 설명  
 검색에서 대\/소문자를 구분하지 않도록 하는 `i` 플래그도 설정할 수 있습니다.  
  
## 예제  
 다음 예제는 **search** 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var src = "is but a Dream within a dream";  
var re = /dream/;  
var pos = src.search(re);  
document.write(pos);  
document.write("<br/>");  
  
re = /dream/i;  
pos = src.search(re);  
document.write(pos);  
  
// Output:   
// 24   
// 9  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [String 개체](../../javascript/reference/string-object-javascript.md)  
  
## 참고 항목  
 [exec 메서드\(Regular Expression\)](../../javascript/reference/exec-method-regular-expression-javascript.md)   
 [match 메서드\(String\)](../../javascript/reference/match-method-string-javascript.md)   
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [Regular Expression Syntax \(JavaScript\)](http://msdn.microsoft.com/ko-kr/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [replace 메서드\(String\)](../../javascript/reference/replace-method-string-javascript.md)   
 [test 메서드\(Regular Expression\)](../../javascript/reference/test-method-regular-expression-javascript.md)   
 [Regular Expression Programming \(JavaScript\)](http://msdn.microsoft.com/ko-kr/3b62e27c-4f07-4726-a95b-6e841807bfaf)