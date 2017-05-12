---
title: "String.raw 함수(JavaScript) | Microsoft Docs"
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
ms.assetid: b1038b73-3944-4645-b075-3a674b313762
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# String.raw 함수(JavaScript)
템플릿 문자열의 원시 문자열을 반환합니다.  
  
## 구문  
  
```  
String.raw`templateStr`;  
String.raw(obj, ...substitutions);  
```  
  
#### 매개 변수  
 `templateStr`  
 필수.  템플릿 문자열입니다.  
  
 `obj`  
 필수.  {raw: 'value'} 등의 개체 리터럴 표기법을 사용하여 지정한 올바른 형식의 개체입니다.  
  
 `...substitutions`  
 선택 사항입니다.  하나 이상의 대체 값으로 이루어진 배열\([rest 매개 변수](../../javascript/functions-javascript.md)\)입니다.  
  
## 설명  
 `String.raw` 함수는 [템플릿 문자열](../../javascript/advanced/template-strings-javascript.md)과 함께 사용하기 위한 용도입니다.  원시 문자열은 문자열에 있는 모든 이스케이프 문자 및 백슬래시를 포함합니다.  
  
 `obj`가 올바른 형식의 개체가 아닌 경우 오류가 발생합니다.  
  
## 예제  
  
```  
function log(arg) {  
    if(console && console.log) {  
        console.log(arg);  
    }  
};  
  
var name = "bob";  
  
log(`hello \t${name}`);  
log(String.raw`hello \t${name}`);  
// The following usage for String.raw is supported but  
// is not typical.  
log(String.raw({ raw: 'fred'}, 'F', 'R', 'E'));  
  
// Output:  
// hello   bob  
// hello \tbob  
// fFrReEd  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]