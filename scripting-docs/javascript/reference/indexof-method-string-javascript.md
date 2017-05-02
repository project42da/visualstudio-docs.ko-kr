---
title: "indexOf 메서드(String)(JavaScript) | Microsoft Docs"
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
  - "indexOf"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "indexOf 메서드, string"
  - "string, indexOf 메서드"
ms.assetid: a17372fa-669b-471b-9240-46927a265152
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 18
---
# indexOf 메서드(String)(JavaScript)
처음으로 나오는 부분 문자열의 위치를 반환합니다.  
  
## 구문  
  
```  
  
strObj. indexOf(subString[, startIndex])  
```  
  
## 매개 변수  
 `strObj`  
 필수입니다.  `String` 개체 또는 문자열 리터럴입니다.  
  
 `subString`  
 필수입니다.  문자열에서 검색할 부분 문자열입니다.  
  
 `startIndex`  
 선택 사항  `String` 개체의 검색을 시작할 인덱스입니다.  생략하면 문자열의 처음부터 검색을 시작합니다.  
  
## 설명  
 **indexOf** 메서드는 `String` 개체에서 부분 문자열의 시작을 반환합니다.  부분 문자열이 없으면 \-1이 반환됩니다.  
  
 `startindex`가 음수이면 `startindex`는 0으로 처리되고,  startindex가 가장 큰 인덱스보다 크면 가장 큰 인덱스로 처리됩니다.  
  
 검색은 왼쪽에서 오른쪽으로 수행됩니다.  이 점을 제외하면 이 메서드는 **lastIndexOf**와 같습니다.  
  
## 예제  
 다음 예제는 **indexOf** 메서드의 사용 예를 보여줍니다.  
  
```javascript  
var str = "original equipment manufacturer";  
  
var s = "equip is at position " + str.indexOf("equip");  
s += "<br />";  
s += "abc is at position " + str.indexOf("abc");  
  
document.write(s);  
  
// Output:  
// equip is at position 9  
// abc is at position -1  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [String 개체](../../javascript/reference/string-object-javascript.md)  
  
## 참고 항목  
 [lastIndexOf 메서드\(String\)](../../javascript/reference/lastindexof-method-string-javascript.md)   
 [스크롤, 이동 및 확대\/축소 샘플 응용 프로그램](http://code.msdn.microsoft.com/ie/Scrolling-panning-and-6834aaf9)