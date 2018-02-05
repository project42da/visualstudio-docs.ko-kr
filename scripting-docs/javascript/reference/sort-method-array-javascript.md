---
title: "sort 메서드 (Array) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sort
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Sort method
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0462e60e623b99af458beb61eb7ef4215fe8ef41
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2018
---
# <a name="sort-method-array-javascript"></a>sort 메서드(Array)(JavaScript)
정렬 된 `Array`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
arrayobj.sort(sortFunction)   
```  
  
## <a name="parameters"></a>매개 변수  
 `arrayObj`  
 필수. 모든 `Array` 개체입니다.  
  
 `sortFunction`  
 선택 사항입니다. 요소의 순서를 결정 하는 데 사용 되는 함수의 이름입니다. 생략 하면 요소 ASCII 문자 순서가 오름차순으로 정렬 됩니다.  
  
## <a name="return-value"></a>반환 값  
 정렬 된 배열입니다.  
  
## <a name="remarks"></a>설명  
 `sort` 메서드 종류는 `Array` 직접 개체; 아니요 새로운 `Array` 실행 하는 동안 개체가 만들어집니다.  
  
 `sortFunction`두 인수를 사용 하 고 다음 값 중 하나를 반환 해야 합니다.  
  
-   음수 값 (0 보다 작음) 첫 번째 인수로 전달 하는 경우이 두 번째 인수 보다 합니다.  첫 번째 인수는 더 낮은 인덱스에서 정렬 됩니다.
  
-   영 (0)는 두 개의 인수는 해당 하는 경우.  두 개의 인수는 배열에 있는 다른 요소와 관련 하 여 정렬 되지만 서로 대해 정렬 되지 않습니다.
  
-   0 보다 큰 () 첫 번째 인수가 두 번째 인수 보다 큰 양의 값입니다.  두 번째 인수는 더 낮은 인덱스에서 정렬 됩니다.
  
## <a name="example"></a>예  
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