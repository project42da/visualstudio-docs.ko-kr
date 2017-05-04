---
title: "Comment 문(JavaScript) | Microsoft Docs"
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
  - "Comment_JavaScript"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "주석 문"
  - "주석, 무시"
ms.assetid: b604824f-ac17-49d3-bcdb-2a893ab5fff8
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# Comment 문(JavaScript)
주석이 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 파서에서 무시되도록 합니다.  
  
## 구문  
  
```  
Single-line Comment:  
// comment   
```  
  
```  
Multiline Comment:  
/*  
comment  
*/  
```  
  
```  
Comments with conditional compilation:  
//@CondStatement   
  
/*@  
condStatement  
@*/  
```  
  
## 설명  
 `comment` 인수는 스크립트에 포함할 주석의 텍스트입니다.  `condStatement` 인수는 조건부 컴파일이 활성화될 경우 사용됩니다.  한 줄 주석을 사용하면 "\/\/" 문자와 "@" 문자 사이에 공백이 없을 수 있습니다.  
  
 주석을 사용하여 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 파서가 스크립트 부분을 읽지 못하도록 합니다.  주석을 사용하여 자세한 설명을 프로그램에 포함할 수 있습니다.  
  
 한 줄 주석을 사용하면 파서가 주석 마커와 줄 끝 사이에 있는 모든 텍스트를 무시합니다.  여러 줄 주석을 사용하면 파서가 마커의 시작과 끝 사이에 있는 모든 텍스트를 무시합니다.  
  
 주석은 해당 기능을 지원하지 않는 브라우저와 호환성을 유지하면서 조건부 컴파일을 지원하는 데 사용됩니다.  이들 브라우저에서는 해당 주석 형식을 각각 한 줄 또는 여러 줄 주석으로 처리합니다.  
  
## 예제  
 다음 예제에서는 주석의 가장 일반적인 사용을 보여 줍니다.  
  
```javascript  
/* This is a multiline comment that  
    can span as many lines as necessary.  */  
function myfunction(arg1, arg2){  
    var r;  
    // This is a single line comment.  
    r = arg1 + arg2  
    return(r);  
}  
```  
  
## 예제  
 다음 예제에서는 조건부 컴파일을 사용하는 방법을 보여 줍니다.  이 예제에서는 조건부 컴파일이 `@cc_on` 문에서 활성화될 경우에만 사용되는 특수 주석 구분 기호를 사용합니다.  조건부 컴파일을 지원하지 않는 스크립팅 엔진은 조건부 컴파일이 지원되지 않는다고 언급된 메시지만 확인합니다.  
  
```javascript  
/*@cc_on @*/  
/*@if (@_jscript_version >= 4)  
    alert("JavaScript version 4 or better");  
    @else @*/  
    alert("Conditional compilation not supported by this scripting engine.");  
/*@end @*/  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]