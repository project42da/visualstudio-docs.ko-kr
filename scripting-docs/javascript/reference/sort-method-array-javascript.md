---
title: "sort 메서드 (Array) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: sort
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: Sort method
ms.assetid: 9bd8b54a-c838-4806-85c8-62eebe6bc48c
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2d098b47591ca7bbb4e3e8da5e5c14f8c0e9b255
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="sort-method-array-javascript"></a>sort 메서드(Array)(JavaScript)
정렬 된 `Array`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
arrayobj.sort(sortFunction)   
```  
  
## <a name="parameters"></a>매개 변수  
 `arrayObj`  
 필수 요소. 모든 `Array` 개체입니다.  
  
 `sortFunction`  
 선택 사항입니다. 요소의 순서를 결정 하는 데 사용 되는 함수의 이름입니다. 생략 하면 요소 ASCII 문자 순서가 오름차순으로 정렬 됩니다.  
  
## <a name="return-value"></a>반환 값  
 정렬 된 배열입니다.  
  
## <a name="remarks"></a>설명  
 `sort` 메서드 종류는 `Array` 직접 개체; 아니요 새로운 `Array` 실행 하는 동안 개체가 만들어집니다.  
  
 에 함수를 제공 하는 경우는 `sortFunction` 인수를 반환 해야 합니다는 다음 값 중 하나:  
  
-   첫 번째 인수를 전달 하는 경우 음수 값을 두 번째 인수 보다 작은 경우  
  
-   두 개의 인수는 해당 하는 경우 0입니다.  
  
-   첫 번째 인수가 두 번째 인수 보다 큰 양의 값입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `sort` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var a = new Array(4, 11, 2, 10, 3, 1);  
  
var b = a.sort();  
document.write(b);  
document.write("<br/>");  
  
// This is ASCII character order.  
// Output: 1,10,11,2,3,4)  
  
// Sort the array elements with a function that compares array elements.  
b = a.sort(CompareForSort);  
document.write(b);  
document.write("<br/>");  
// Output: 1,2,3,4,10,11.  
  
// Sorts array elements in ascending order numerically.  
function CompareForSort(first, second)  
{  
    if (first == second)  
        return 0;  
    if (first < second)  
        return -1;  
    else  
        return 1;   
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]