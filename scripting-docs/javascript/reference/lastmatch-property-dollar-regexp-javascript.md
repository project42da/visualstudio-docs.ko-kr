---
title: "lastMatch 속성($&amp;)(RegExp)(JavaScript) | Microsoft Docs"
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
  - "$&"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "lastMatch 속성($%)"
  - "lastMatch 속성($&)"
ms.assetid: d223836d-5235-48a5-a926-d20764ad3f14
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# lastMatch 속성($&amp;)(RegExp)(JavaScript)
정규식 검색에서 마지막으로 일치하는 문자를 반환합니다.  읽기 전용입니다.  
  
## 구문  
  
```  
  
RegExp.lastMatch  
```  
  
## 설명  
 이 속성과 연결된 개체는 항상 전역 `RegExp` 개체입니다.  
  
 `lastMatch` 속성의 초기 값은 빈 문자열입니다.  `lastMatch` 속성 값은 일치하는 값을 찾을 때마다 변경됩니다.  
  
## 예제  
 다음 예제에서는 `lastMatch` 속성의 사용법을 보여 줍니다.  
  
```javascript  
// Create the regular expression pattern.  
var re = new RegExp("d(b+)(d)","ig");  
var str = "cdbBdbsbdbdz";  
  
// Perform the search.  
var arr = re.exec(str);  
  
// Print the output.  
var s = ""   
s += "$1: " + RegExp.$1 + "<br />";  
s += "$2: " + RegExp.$2 + "<br />";  
s += "$3: " + RegExp.$3 + "<br />";  
s += "input: " + RegExp.input + "<br />";  
s += "lastMatch: " + RegExp.lastMatch + "<br />";  
s += "leftContext: " + RegExp.leftContext + "<br />";  
s += "rightContext: " + RegExp.rightContext + "<br />";   
s += "lastParen: " + RegExp.lastParen + "<br />";  
  
document.write(s);  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)  
  
## 참고 항목  
 [$1...$9 속성\(RegExp\)](../../javascript/reference/dollar-1-dot-dot-dot-dollar-9-properties-regexp-javascript.md)   
 [index 속성\(RegExp\)](../../javascript/reference/index-property-regexp-javascript.md)   
 [input 속성\($\_\)\(RegExp\)](../../javascript/reference/input-property-dollar-regexp-javascript.md)   
 [lastIndex 속성\(RegExp\)](../../javascript/reference/lastindex-property-regexp-javascript.md)   
 [lastParen 속성\($\+\)\(RegExp\)](../../javascript/reference/lastparen-property-dollar-regexp-javascript.md)   
 [leftContext 속성\($\`\)\(RegExp\)](../../javascript/reference/leftcontext-property-dollar-grave-regexp-javascript.md)   
 [rightContext 속성\($'\)\(RegExp\)](../../javascript/reference/rightcontext-property-dollar-regexp-javascript.md)