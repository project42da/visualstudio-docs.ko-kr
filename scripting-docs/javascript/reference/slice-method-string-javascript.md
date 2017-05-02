---
title: "slice 메서드(String)(JavaScript) | Microsoft Docs"
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
  - "slice"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "slice 메서드"
  - "문자열[Visual Studio], 문자 반환"
ms.assetid: 80cd77a6-3718-492e-8e96-f909d8721d91
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# slice 메서드(String)(JavaScript)
문자열의 일정 부분을 반환합니다.  
  
## 구문  
  
```  
  
stringObj.slice(start, [end])   
```  
  
## 매개 변수  
 `stringObj`  
 필수 요소.  `String` 개체 또는 문자열 리터럴입니다.  
  
 `start`  
 필수 요소.  `stringObj`에 지정된 부분의 시작을 나타내는 인덱스입니다.  
  
 `end`  
 선택 사항입니다.  `stringObj`에 지정된 부분의 끝을 나타내는 인덱스입니다.  부분 문자열은 `end`로 표시된 문자 앞까지만 포함합니다.  이 값을 지정하지 않으면 `stringObj`의 끝까지 부분 문자열이 계속됩니다.  
  
## 설명  
 `slice` 메서드는 `stringObj`의 지정된 부분을 포함하는 `String` 개체를 반환합니다.  
  
 `slice` 메서드는 `end`로 표시된 문자 앞까지만 복사하고 해당 문자는 포함하지 않습니다.  
  
 `start`가 음수이면 *length* \+ `start`로 처리됩니다. 여기서 *length*는 배열의 길이입니다.  `end`가 음수이면 *length* \+ `end`로 처리되고,  `end`를 생략하면 `stringObj`의 끝까지 계속 복사됩니다.  `end`가 `start` 앞에 나오면 새로운 문자열에 아무 문자도 복사되지 않습니다.  
  
## 예제  
 첫 번째 예제에서 `slice` 메서드는 전체 문자열을 반환합니다.  두 번째 예제에서 `slice` 메서드는 마지막 문자를 제외하고 전체 문자열을 반환합니다.  
  
```javascript  
var str1 = "all good boys do fine";  
  
var slice1 = str1.slice(0);  
var slice2 = str1.slice(0,-1);  
var slice3 = str1.slice(4);  
var slice4 = str1.slice(4, 8);  
  
document.write(slice1 + "<br/>");  
document.write(slice2 + "<br/>");  
document.write(slice3 + "<br/>");  
document.write(slice4);  
  
// Output:  
// all good boys do fine  
// all good boys do fin  
// good boys do fine  
// good  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [String 개체](../../javascript/reference/string-object-javascript.md)  
  
## 참고 항목  
 [slice 메서드\(Array\)](../../javascript/reference/slice-method-array-javascript.md)