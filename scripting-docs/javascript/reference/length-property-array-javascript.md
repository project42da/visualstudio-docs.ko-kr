---
title: "length 속성(Array)(JavaScript) | Microsoft Docs"
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
  - "length Property"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Array 개체"
  - "Length 속성"
  - "length 속성(array)"
ms.assetid: e1c6377c-2e84-440a-9660-f1f512e4a938
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# length 속성(Array)(JavaScript)
배열의 길이를 가져오거나 설정합니다.  배열에 정의된 요소의 최고값보다 하나 큰 숫자입니다.  
  
## 구문  
  
```  
  
numVar = arrayObj.length   
```  
  
## 매개 변수  
 `numVar`  
 필수 요소.  모든 숫자입니다.  
  
 `arrayObj`  
 필수 요소.  모든 `Array` 개체입니다.  
  
## 설명  
 JavaScript에서 배열이 스파스이며 배열의 요소는 연속일 필요가 없습니다.  `length` 속성이 배열에서 요소 수일 필요는 없습니다.  예를 들어 다음 배열 정의에서 `my_array.length`에는 2가 아닌 7이 포함됩니다.  
  
```javascript  
var my_array = new Array( );  
my_array[0] = "Test";  
my_array[6] = "Another Test";  
```  
  
 `length` 속성을 이전 값보다 작게 설정하면 배열이 잘리고 배열 인덱스가 `length` 속성의 새 값보다 크거나 같은 모든 요소가 손실됩니다.  
  
 길이 속성을 이전 값보다 크게 설정하면 배열이 확장되고 생성된 새 요소에 `undefined` 값이 포함됩니다.  
  
 다음 예제에서는 `length` 속성을 사용하는 방법을 보여 줍니다.  
  
```javascript  
var a;  
a = new Array(0,1,2,3,4);  
document.write(a.length);  
  
// Output  
// 5  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
> [!NOTE]
>  Internet Explorer 9 Standards 모드부터 배열 초기화에 포함된 후행 쉼표는 다르게 처리됩니다.