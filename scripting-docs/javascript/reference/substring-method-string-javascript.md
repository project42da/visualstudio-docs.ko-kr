---
title: "substring 메서드(String)(JavaScript) | Microsoft Docs"
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
  - "substring"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "부분 문자열"
  - "substring 메서드"
ms.assetid: 9cf9a005-cbe3-42fd-828b-57a39f54224c
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 18
---
# substring 메서드(String)(JavaScript)
`String` 개체 안의 지정된 위치에 있는 부분 문자열을 반환합니다.  
  
## 구문  
  
```  
  
      strVariable. substring(start [, end])  
"String Literal".substring(start [, end])   
```  
  
## 매개 변수  
 `start`  
 필수 요소.  부분 문자열의 시작을 나타내는 0부터 시작하는 인덱스입니다.  
  
 `end`  
 선택 사항입니다.  부분 문자열의 끝을 나타내는 0부터 시작하는 인덱스입니다.  부분 문자열은 `end`로 표시된 문자 앞까지만 포함합니다.  
  
 `end`가 생략된 경우 `start`에서 원래 문자열 마지막까지의 문자가 반환됩니다.  
  
## 설명  
 `substring` 메서드는 `start`에서 `end`까지\(end는 포함 안 함\) 부분 문자열을 포함하는 문자열을 반환합니다.  
  
 **substring** 메서드는 부분 문자열의 시작점으로 `start`와 `end` 중 낮은 값을 사용합니다.  예를 들어, strvar.substring\(0, 3**\)** 및 strvar.substring\(3, 0\)은 같은 부분 문자열을 반환합니다.  
  
 `start`나 `end`가 `NaN` 또는 음수이면 0으로 바뀝니다.  
  
 부분 문자열의 길이는 `start`와 `end` 사이의 차이에 대한 절대값과 같습니다.  예를 들어 strvar.substring\(0, 3\)과 strvar.substring\(3, 0\)에서 반환되는 부분 문자열의 길이는 3입니다.  
  
## 예제  
 다음 예제는 **substring** 메서드의 사용 예를 보여 줍니다.  
  
```javascript  
var s = "The quick brown fox jumps over the lazy dog.";  
var ss = s.substring(10, 15);  
document.write(ss);  
  
// Output:  
// brown  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [substr 메서드\(String\)](../../javascript/reference/substr-method-string-javascript.md)