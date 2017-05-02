---
title: "RegExp 개체(JavaScript) | Microsoft Docs"
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
  - "RegExp"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "RegExp 개체"
  - "RegExp 개체, 개요"
ms.assetid: 7f6b1073-8cbb-49ed-94b6-56833ba663c5
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# RegExp 개체(JavaScript)
정규식 패턴 검색 결과에 관한 정보를 저장하는 내장 전역 개체입니다.  
  
## 구문  
  
```  
  
RegExp.property   
```  
  
## 설명  
 필수 *property* 인수는 `RegExp` 개체 속성 중 하나일 수 있습니다.  
  
 `RegExp` 개체를 직접 만들 수는 없지만 항상 사용할 수는 있습니다.  정규식 검색을 성공적으로 완료할 때까지 `RegExp` 개체의 여러 속성 초기 값은 다음과 같습니다.  
  
|속성|속기|초기 값|  
|--------|--------|----------|  
|index||\-1|  
|input|$\_|빈 문자열|  
|lastIndex||\-1|  
|lastMatch|$&|빈 문자열|  
|lastParen|$\+|빈 문자열|  
|leftContext|$\`|빈 문자열|  
|rightContext|$'|빈 문자열|  
|$1 \- $9|$1 \- $9|빈 문자열|  
  
 정규식 검색을 성공적으로 완료할 때까지 속성의 값은 undefined입니다.  
  
 전역 `RegExp` 개체를 **Regular Expression** 개체와 혼동해서는 안됩니다.  이 두 개체는 동일하게 보이지만 별개의 것으로 뚜렷하게 구별됩니다.  전역 `RegExp` 개체의 속성에는 일치하는 것이 있을 때마다 끊임없이 업데이트되는 정보가 들어 있지만 **Regular Expression** 개체의 속성에는 그 **Regular Expression**의 해당 인스턴스에 일치하는 정보만 들어 있습니다.  
  
## 예제  
 다음 예제에서는 정규식 검색을 수행합니다.  `exec` 메서드에서 반환된 배열에서 찾은 전역 `RegExp` 개체의 일치 항목 및 하위 일치 항목을 표시합니다.  
  
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
  
<a name="js56jsobjregexpprop"></a>   
## 속성  
 [$1...$9 속성](../../javascript/reference/dollar-1-dot-dot-dot-dollar-9-properties-regexp-javascript.md) &#124; [index 속성](../../javascript/reference/index-property-regexp-javascript.md) &#124; [input 속성](../../javascript/reference/input-property-dollar-regexp-javascript.md) &#124; [lastIndex 속성](../../javascript/reference/lastindex-property-regexp-javascript.md) &#124; [lastMatch 속성](../../javascript/reference/lastmatch-property-dollar-regexp-javascript.md) &#124; [lastParen 속성](../../javascript/reference/lastparen-property-dollar-regexp-javascript.md) &#124; [leftContext 속성](../../javascript/reference/leftcontext-property-dollar-grave-regexp-javascript.md) &#124; [rightContext 속성](../../javascript/reference/rightcontext-property-dollar-regexp-javascript.md)  
  
## 메서드  
 `RegExp` 개체에는 메서드가 없습니다.  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## 참고 항목  
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [Regular Expression Syntax \(JavaScript\)](http://msdn.microsoft.com/ko-kr/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [String 개체](../../javascript/reference/string-object-javascript.md)