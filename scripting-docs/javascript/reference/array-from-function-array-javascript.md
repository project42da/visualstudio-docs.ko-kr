---
title: "Array.from 함수 (Array) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1bf59a99-f860-4c4d-b4c6-d5f1f946a490
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a240cb439942bfeb6b4c9a1febb4d24cef1c5c18
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="arrayfrom-function-array-javascript"></a>Array.from 함수(Array)(JavaScript)
배열 형식의 개체나 반복 가능한 개체에서 배열을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Array.from (arrayLike [ , mapfn [ , thisArg ] ] );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `arrayLike`  
 필수 요소. 배열 형식의 개체나 반복 가능한 개체입니다.  
  
 `mapfn`  
 선택 사항입니다. `arrayLike`의 각 요소에 대해 호출할 매핑 함수입니다.  
  
 `thisArg`  
 선택 사항입니다. 매핑 함수에 `this` 개체를 지정합니다.  
  
## <a name="remarks"></a>설명  
 `arrayLike` 매개 변수는 인덱싱된 요소 및 `length` 속성을 가진 개체이거나 `Set` 개체와 같은 반복 가능한 개체여야 합니다.  
  
 선택적 매핑 함수는 배열의 각 요소에 대해 호출됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 DOM 요소 노드 컬렉션에서 배열을 반환합니다.  
  
```JavaScript  
var elemArr = Array.from(document.querySelectorAll('*'));  
var elem = elemArr[0]; // elem contains a reference to the first DOM element  
  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 문자 배열을 반환합니다.  
  
```JavaScript  
var charArr = Array.from("abc");  
// charArr[0] == "a";  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 컬렉션에 포함된 개체의 배열을 반환합니다.  
  
```JavaScript  
var setObj = new Set("a", "b", "c");  
var objArr = Array.from(setObj);  
// objArr[1] == "b";   
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 화살표 구문 및 매핑 함수를 사용하여 요소의 값을 변경하는 방법을 보여 줍니다.  
  
```JavaScript  
var arr = Array.from([1, 2, 3], x => x * 10);  
// arr[0] == 10;  
// arr[1] == 20;  
// arr[2] == 30;  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]