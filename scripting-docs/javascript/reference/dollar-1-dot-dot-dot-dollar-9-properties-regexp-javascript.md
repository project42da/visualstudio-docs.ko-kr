---
title: "$1...$9 속성(RegExp)(JavaScript) | Microsoft Docs"
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
  - "$1...$9"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "$1...$9 속성"
ms.assetid: 8bd84851-f62f-4eb1-a93d-b67135ea091a
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 18
---
# $1...$9 속성(RegExp)(JavaScript)
패턴 일치 과정에서 찾아 가장 최근에 저장한 9개 부분을 반환합니다.  읽기 전용입니다.  
  
## 구문  
  
```  
  
RegExp.$n   
```  
  
## 매개 변수  
 `RegExp`  
 항상 전역 `RegExp` 개체입니다.  
  
 `n`  
 1부터 9까지의 정수입니다.  
  
## 설명  
 **$1...$9** 속성 값은 괄호 안에서 일치하는 내용을 찾을 때마다 수정됩니다.  정규식 패턴에 지정할 수 있는 괄호 안의 부분 문자열 수에는 제한이 없지만 저장되는 것은 최근 9개뿐입니다.  
  
## 예제  
 다음 예제에서는 정규식 검색을 수행합니다.  전역 `RegExp` 개체에서 찾은 일치하는 항목 및 하위 일치 항목을 표시합니다.  하위 일치 항목은 `$1…$9` 속성에 포함된 성공적으로 괄호로 묶인 일치 항목입니다.  이 예제에서는 또한 `exec` 메서드에서 반환된 배열에서 찾은 일치 항목 및 하위 일치 항목을 표시합니다.  
  
```javascript  
var newLine = "<br />";  
  
var re = /(\w+)@(\w+)\.(\w+)/g  
var src = "Please send mail to george@contoso.com and someone@example.com. Thanks!"  
  
var result;  
var s = "";  
  
// Get the first match.  
result = re.exec(src);  
  
while (result != null) {  
    // Show the entire match.  
    s += newLine;  
  
    // Show the match and submatches from the RegExp global object.  
    s += "RegExp.lastMatch: " + RegExp.lastMatch + newLine;  
    s += "RegExp.$1: " + RegExp.$1 + newLine;  
    s += "RegExp.$2: " + RegExp.$2 + newLine;  
    s += "RegExp.$3: " + RegExp.$3 + newLine;  
  
    // Show the match and submatches from the array that is returned  
    // by the exec method.  
    for (var index = 0; index < result.length; index++) {  
        s +=  index + ": ";  
        s += result[index];  
        s += newLine;  
    }  
  
    // Get the next match.  
    result = re.exec(src);  
}  
document.write(s);  
  
// Output:  
//  RegExp.lastMatch: george@contoso.com  
//  RegExp.$1: george  
//  RegExp.$2: contoso  
//  RegExp.$3: com  
//  0: george@contoso.com  
//  1: george  
//  2: contoso  
//  3: com  
  
//  RegExp.lastMatch: someone@example.com  
//  RegExp.$1: someone  
//  RegExp.$2: example  
//  RegExp.$3: com  
//  0: someone@example.com  
//  1: someone  
//  2: example  
//  3: com  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)  
  
## 참고 항목  
 [Regular Expression Syntax \(JavaScript\)](http://msdn.microsoft.com/ko-kr/ab0766e1-7037-45ed-aa23-706f58358c0e)