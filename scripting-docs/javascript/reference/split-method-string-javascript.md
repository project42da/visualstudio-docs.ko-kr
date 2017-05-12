---
title: "split 메서드(String)(JavaScript) | Microsoft Docs"
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
  - "split"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "split 메서드"
ms.assetid: 7f093336-c887-4efb-b91f-819b6d18a181
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# split 메서드(String)(JavaScript)
지정된 구분 기호를 사용하여 문자열을 부분 문자열로 분할하고 배열로 반환합니다.  
  
## 구문  
  
```  
  
stringObj.split([separator[, limit]])  
```  
  
## 매개 변수  
 `stringObj`  
 필수입니다.  분할할 `String` 개체 또는 문자열 리터럴입니다.  이 개체는 **split** 메서드로 수정되지 않습니다.  
  
 `separator`  
 선택 사항  문자열이나 문자열을 구분하는 데 사용하는 하나 이상의 문자를 나타내는 **Regular Expression** 개체입니다.  생략하면 전체 문자열을 포함하는 단일 요소 배열이 반환됩니다.  
  
 `limit`  
 선택 사항  배열로 반환되는 요소의 수를 제한하는 값입니다.  
  
## 반환 값  
 **split** 메서드의 결과는 `separator`가 발생하는 `stringObj`의 각 지점에서 분할된 문자열의 배열입니다.  `separator`는 어느 배열의 요소로도 반환되지 않습니다.  
  
## 예제  
 다음 예제는 **split** 메서드의 사용 예를 보여줍니다.  
  
```javascript  
var s = "The quick brown fox jumps over the lazy dog.";  
var ss = s.split(" ");  
for (var i in ss) {  
    document.write(ss[i]);  
    document.write("<br/>");  
}  
  
// Output:   
// The  
// quick  
// brown  
// fox  
// jumps  
// over  
// the  
// lazy  
// dog.  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [String 개체](../../javascript/reference/string-object-javascript.md)  
  
## 참고 항목  
 [concat 메서드\(String\)](../../javascript/reference/concat-method-string-javascript.md)   
 [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)   
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [Regular Expression Syntax \(JavaScript\)](http://msdn.microsoft.com/ko-kr/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [스크롤, 이동 및 확대\/축소 샘플 응용 프로그램](http://code.msdn.microsoft.com/ie/Scrolling-panning-and-6834aaf9)