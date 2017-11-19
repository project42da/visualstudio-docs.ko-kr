---
title: "indexOf 메서드 (Array) (JavaScript) | Microsoft Docs"
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
helpviewer_keywords:
- arrays [JavaScript], indexOf method
- indexOf method [JavaScript]
ms.assetid: 5bee31ae-aaf1-4466-8cfd-ed287e3cdf17
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 63685219faf42991da6b798493c58b356ab97279
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="indexof-method-array-javascript"></a>indexOf 메서드(Array)(JavaScript)
배열에서 맨 처음 나오는 값의 인덱스를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
array1.indexOf(searchElement[, fromIndex])  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|정의|  
|---------------|----------------|  
|`array1`|필수 요소. 배열 개체입니다.|  
|`searchElement`|필수 요소. 찾을 값 `array1`합니다.|  
|`fromIndex`|선택 사항입니다. 검색을 시작 하는 배열 인덱스입니다. 경우 `fromIndex` 는 검색을 생략 하면 인덱스 0에서 시작 합니다.|  
  
## <a name="return-value"></a>반환 값  
 첫 번째 발생의 인덱스 `searchElement` 는 배열 또는 경우-1의 `searchElement` 찾을 수 없습니다.  
  
## <a name="remarks"></a>설명  
 `indexOf` 메서드는 지정된 된 값에 대 한 배열을 검색 합니다. 메서드는 지정된 된 값을 찾을 수 없는 경우 첫 번째 발생의 인덱스를 반환 합니다.  
  
 검색 오름차순 인덱스 순서로 발생 합니다.  
  
 배열 요소와 비교 됩니다는 `searchElement` 비슷합니다 완전 같음, 값은 `===` 연산자입니다. 자세한 내용은 참조 [비교 연산자](../../javascript/reference/comparison-operators-javascript.md)합니다.  
  
 선택적 `fromIndex` 인수 검색을 시작 하는 배열 인덱스를 지정 합니다. 경우 `fromIndex` 보다 크면 또는 배열 길이 같으면-1 반환 됩니다. 경우 `fromIndex` 가 음수 이면 검색에서 시작 더하기 배열 길이 `fromIndex`합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 사용을 보여 주기는 `indexOf` 메서드.  
  
```JavaScript  
// Create an array. (The elements start at index 0.)  
var ar = ["ab", "cd", "ef", "ab", "cd"];  
  
// Determine the first location of "cd".  
document.write(ar.indexOf("cd") + "<br/>");  
  
// Output: 1  
  
// Find "cd" starting at index 2.  
document.write(ar.indexOf("cd", 2) + "<br/>");  
  
// Output: 4  
  
// Find "gh" (which is not found).  
document.write (ar.indexOf("gh")+ "<br/>");  
  
// Output: -1  
  
// Find "ab" with a fromIndex argument of -2.  
// The search starts at index 3, which is the array length plus -2.  
document.write (ar.indexOf("ab", -2) + "<br/>");  
// Output: 3  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [JavaScript 메서드](../../javascript/reference/javascript-methods.md)   
 [Array 개체](../../javascript/reference/array-object-javascript.md)   
 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)