---
title: "Array.of 함수 (Array) (JavaScript) | Microsoft Docs"
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
ms.assetid: 2884dda3-65d1-4990-9afe-87865c2d4f7f
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 042315bbc3b956e92fff866f7d403b6f87726a74
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="arrayof-function-array-javascript"></a>Array.of 함수(Array)(JavaScript)
전달된 인수에서 배열을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Array.of(element0[, element1][, ...][,elementN]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `element0,...,elementN`  
 선택 사항입니다. 배열에 삽입할 요소입니다. n + 1개의 요소를 포함하고 길이가 n + 1인 배열이 생성됩니다.  
  
## <a name="remarks"></a>설명  
 이 함수는 `new Array(args)` 호출과 비슷하지만 `Array.of`는 하나의 인수가 전달된 경우 특수 동작을 포함하지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 전달된 숫자에서 배열을 만듭니다.  
  
```JavaScript  
var arr = Array.of(1, 2, 3);  
// arr[0] == 1   
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Array.of` 및 `new Array` 사용의 차이점을 보여 줍니다.  
  
```JavaScript  
var arr1 = Array.of(3);  
// arr1[0] == 3  
  
// With new Array, a single argument specifies  
// the length of the new array.  
var arr2 = new Array(3);  
// arr2[0] is undefined  
// arr2.length == 3  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]