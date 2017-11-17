---
title: "lastIndexOf 메서드 (Array) (JavaScript) | Microsoft Docs"
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
- arrays [JavaScript], lastIndexOf method
- lastIndexOf method [JavaScript]
ms.assetid: 04f5145d-007e-498f-b06f-11ab384c2968
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 12d2a0fca7a7cd82543a83ea19aca49d3cbb93b6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="lastindexof-method-array-javascript"></a>lastIndexOf 메서드(Array)(JavaScript)
배열에서 마지막으로 나오는 지정된 값의 인덱스를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
array1.lastIndexOf(searchElement[, fromIndex])  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|정의|  
|---------------|----------------|  
|`array1`|필수 요소. 검색할 배열 개체입니다.|  
|`searchElement`|필수 요소. 찾을 값 `array1`합니다.|  
|`fromIndex`|선택 사항입니다. 검색을 시작 하는 배열 인덱스입니다. 경우 `fromIndex` 는 검색을 생략 하면 배열에서 마지막 인덱스에서 시작 합니다.|  
  
## <a name="return-value"></a>반환 값  
 마지막으로 나타나는 항목의 인덱스 `searchElement` 는 배열 또는 경우-1의 `searchElement` 찾을 수 없습니다.  
  
## <a name="remarks"></a>설명  
 `lastIndexOf` 메서드는 지정된 된 값에 대 한 배열을 검색 합니다. 메서드는 지정된 된 값을 찾을 수 없는 경우 첫 번째 발생의 인덱스를 반환 합니다.  
  
 내림차순 인덱스에서 검색이 수행 (성 멤버 이름). 오름차순을 검색 하려면 사용 하 여는 [indexOf 메서드 (Array)](../../javascript/reference/indexof-method-array-javascript.md)합니다.  
  
 비교할 배열 요소는 `searchElement` 완전 같음, 수행 하는 비교와 유사 하 여 값의 `===` 연산자입니다. 자세한 내용은 참조 [비교 연산자](../../javascript/reference/comparison-operators-javascript.md)합니다.  
  
 선택적 `fromIndex` 인수 검색을 시작 하는 배열 인덱스를 지정 합니다. 경우 `fromIndex` 보다 크면 또는 배열 길이 같을 경우 전체 배열 검색 됩니다. 경우 `fromIndex` 가 음수 이면 검색에서 시작 더하기 배열 길이 `fromIndex`합니다. 계산 된 인덱스가 0 보다 작은 경우-1이 반환 됩니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 사용을 보여 주기는 `lastIndexOf` 메서드.  
  
```JavaScript  
// Create an array.  
var ar = ["ab", "cd", "ef", "ab", "cd"];  
  
// Determine the first location, in descending order, of "cd".  
document.write(ar.lastIndexOf("cd") + "<br/>");  
  
// Output: 4  
  
// Find "cd" in descending order, starting at index 2.  
document.write(ar.lastIndexOf("cd", 2) + "<br/>");  
  
// Output: 1  
  
// Search for "gh" (which is not found).  
document.write(ar.lastIndexOf("gh")+ "<br/>");  
  
// Output: -1  
  
// Find "ab" with a fromIndex argument of -3.  
// The search in descending order starts at index 3,  
// which is the array length minus 2.  
document.write(ar.lastIndexOf("ab", -3) + "<br/>");  
// Output: 0  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [indexOf 메서드 (Array)](../../javascript/reference/indexof-method-array-javascript.md)   
 [Array 개체](../../javascript/reference/array-object-javascript.md)   
 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)