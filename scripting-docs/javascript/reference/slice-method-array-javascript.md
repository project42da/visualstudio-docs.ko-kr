---
title: "slice 메서드(Array)(JavaScript) | Microsoft Docs"
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
  - "0부터 시작하는 인덱스"
  - "Array 개체"
  - "slice 메서드"
ms.assetid: 3c122219-14de-4126-b091-809659c026d6
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# slice 메서드(Array)(JavaScript)
배열의 일정 부분을 반환합니다.  
  
## 구문  
  
```  
  
arrayObj.slice(start, [end])   
```  
  
## 매개 변수  
 `arrayObj`  
 필수 요소.  `Array` 개체입니다.  
  
 `start`  
 필수 요소.  `arrayObj`에 대한 지정된 부분의 시작입니다.  
  
 `end`  
 선택 사항입니다.  `arrayObj`에 대한 지정된 부분의 끝입니다.  
  
## 설명  
 `slice` 메서드는 `arrayObj`의 지정된 부분을 포함하는 `Array` 개체를 반환합니다.  
  
 `slice` 메서드는 `end`로 표시된 요소 앞까지만 복사하고 요소 부분은 포함하지 않습니다.  `start`가 음수이면 `length` \+ `start`로 처리됩니다. 여기서 `length`는 배열의 길이입니다.  `end`가 음수이면 `length` \+ `end`로 처리됩니다. 여기서 `length`는 배열의 길이입니다.  `end`를 생략하면 `arrayObj`의 끝까지 계속 추출됩니다.  `end`가 `start` 앞에 나오면 새로운 배열에 아무 요소도 복사되지 않습니다.  
  
## 예제  
 다음 예제에서는 `slice` 메서드를 사용하는 방법을 보여 줍니다  첫 번째 예제에서 `myArray`의 마지막 요소를 제외한 모든 항목이 `newArray`로 복사됩니다.  두 번째 예제에서는 `myArray`의 마지막 요소 2개만 `newArray`로 복사됩니다.  
  
```javascript  
var origArray = [3, 5, 7, 9];  
var newArray = origArray. slice(0, -1);  
document.write(origArray);  
document.write("<br/>");  
newArray = origArray. slice(-2);  
document.write(newArray);  
  
// Output:  
// 3,5,7,9  
// 7,9  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## 참고 항목  
 [slice 메서드\(String\)](../../javascript/reference/slice-method-string-javascript.md)   
 [String 개체](../../javascript/reference/string-object-javascript.md)