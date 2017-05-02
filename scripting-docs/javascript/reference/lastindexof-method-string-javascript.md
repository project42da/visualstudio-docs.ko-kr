---
title: "lastIndexOf 메서드(String)(JavaScript) | Microsoft Docs"
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
  - "lastIndexOf"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "lastIndexOf 메서드, string"
  - "string, lastIndexOf 메서드"
ms.assetid: 1ed36ccd-0f0b-4f16-be45-0567207670af
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# lastIndexOf 메서드(String)(JavaScript)
문자열에서 마지막으로 나오는 부분 문자열을 반환합니다.  
  
## 구문  
  
```  
  
strObj.lastIndexOf(substring[, startindex])  
```  
  
## 매개 변수  
 `strObj`  
 필수 요소.  `String` 개체 또는 문자열 리터럴입니다.  
  
 `substring`  
 필수 요소.  검색할 부분 문자열입니다.  
  
 `startindex`  
 선택 사항입니다.  검색을 시작할 인덱스입니다.  생략하면 문자열의 끝에서 검색이 시작됩니다.  
  
## 설명  
 **lastIndexOf** 메서드는 `String` 개체 안에서 부분 문자열의 시작점을 나타내는 정수 값을 반환합니다.  부분 문자열이 없으면 \-1이 반환됩니다.  
  
 `startindex`가 음수이면 `startindex`는 0으로 처리됩니다.  startindex가 가장 큰 문자 위치 인덱스보다 크면 사용할 수 있는 가장 큰 인덱스로 처리됩니다.  
  
 문자열의 마지막 문자부터 검색이 수행됩니다.  이 점을 제외하면 이 메서드는 **indexOf**와 같습니다.  
  
 다음 예제는 **lastIndexOf** 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var str = "time, time";  
  
var s = "";  
s += "time is at position " + str.lastIndexOf("time");  
s += "<br />";  
s += "abc is at position " + str.lastIndexOf("abc");  
  
document.write(s);  
  
// Output:  
// time is at position 6  
// abc is at position -1  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [String 개체](../../javascript/reference/string-object-javascript.md)  
  
## 참고 항목  
 [indexOf 메서드\(String\)](../../javascript/reference/indexof-method-string-javascript.md)