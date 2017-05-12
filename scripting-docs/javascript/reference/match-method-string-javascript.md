---
title: "match 메서드(String)(JavaScript) | Microsoft Docs"
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
  - "match"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Match 메서드"
ms.assetid: eda9ad27-4f9b-4cb1-8345-a0ae85979ca0
caps.latest.revision: 22
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 22
---
# match 메서드(String)(JavaScript)
정규식을 사용하여 일치하는 문자열을 검색하고 그 결과를 배열로 반환합니다.  
  
## 구문  
  
```  
  
stringObj.match(rgExp)   
```  
  
## 매개 변수  
 `stringObj`  
 필수 요소.  검색을 수행할 `String` 개체 또는 문자열 리터럴입니다.  
  
 `rgExp`  
 필수 요소.  정규식 패턴 및 적용 가능한 플래그를 포함하는 정규식 개체입니다.  정규식 패턴과 플래그가 포함된 변수 이름이나 문자열 리터럴일 수도 있습니다.  
  
## 설명  
 `match` 메서드가 일치하는 부분을 찾지 못하면 `null`을 반환합니다.  `match` 메서드가 일치하는 부분을 찾으면 배열을 반환하고, 검색 결과를 반영하도록 `RegExp` 개체가 업데이트됩니다.  
  
 전역 플래그\(`g`\)가 설정되지 않은 경우 배열의 0 요소는 일치하는 부분 전체를 포함하고 1 – *n* 요소는 일치하는 부분을 포함합니다.  이 동작은 전역 플래그가 설정되어 있지 않을 때 [exec 메서드\(Regular Expression\)](../../javascript/reference/exec-method-regular-expression-javascript.md) 메서드의 동작과 같습니다.  전역 플래그가 설정되면 0 \- *n* 요소에는 일치하는 모든 대상이 포함됩니다.  
  
 전역 플래그가 설정되지 않은 경우 `match` 메서드에 의해 반환된 배열에 두 개의 속성 `input` 및 `index`가 있습니다.  `input` 속성은 검색된 전체 문자열을 포함합니다.  `index` 속성은 검색된 전체 문자열 내의 일치하는 부분 문자열의 위치를 포함합니다.  
  
 `i` 플래그가 설정되어 있으면 검색이 대\/소문자를 구분하지 않습니다.  
  
## 예제  
 다음 예제에서는 `match` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var src = "azcafAJAC";  
  
var re = /[a-c]/;  
  
var result = src.match(re);  
  
// The entire match is in array element 0.  
document.write(result[0] + "<br/>");  
  
// Now try the same match with the global flag.  
var reg = /[a-c]/g;  
result = src.match(reg);  
  
// The matches are in elements 0 through n.  
for (var index = 0; index < result.length; index++)  
{  
    document.write ("submatch " + index + ": " +  result[index]);  
    document.write("<br />");  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [String 개체](../../javascript/reference/string-object-javascript.md)  
  
## 참고 항목  
 [exec 메서드\(Regular Expression\)](../../javascript/reference/exec-method-regular-expression-javascript.md)   
 [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)   
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [replace 메서드\(String\)](../../javascript/reference/replace-method-string-javascript.md)   
 [search 메서드\(String\)](../../javascript/reference/search-method-string-javascript.md)   
 [test 메서드\(Regular Expression\)](../../javascript/reference/test-method-regular-expression-javascript.md)   
 [Regular Expression Programming \(JavaScript\)](http://msdn.microsoft.com/ko-kr/3b62e27c-4f07-4726-a95b-6e841807bfaf)   
 [Alternation and Subexpressions \(JavaScript\)](http://msdn.microsoft.com/ko-kr/c59dd3e8-7fee-493e-9123-065af1e651ae)   
 [Backreferences \(JavaScript\)](http://msdn.microsoft.com/ko-kr/5d8dbd5a-cd03-4548-850b-9d7bad2c839a)