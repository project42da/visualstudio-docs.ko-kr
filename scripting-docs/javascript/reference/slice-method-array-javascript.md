---
title: "slice 메서드 (Array) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: slice
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- zero-based index
- Array object
- slice method
ms.assetid: 3c122219-14de-4126-b091-809659c026d6
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a61cd331abef9d1a0d979f547f6d6f12222c1eee
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="slice-method-array-javascript"></a>slice 메서드(Array)(JavaScript)
배열의 일정 부분을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
arrayObj.slice(start, [end])   
```  
  
## <a name="parameters"></a>매개 변수  
 `arrayObj`  
 필수 요소. `Array` 개체입니다.  
  
 `start`  
 필수 요소. 지정된 된 부분의 시작 부분 `arrayObj`합니다.  
  
 `end`  
 선택 사항입니다. 지정된 된 부분 끝날 `arrayObj`합니다.  
  
## <a name="remarks"></a>설명  
 `slice` 메서드가 반환 되는 `Array` 의 지정된 된 부분을 포함 하는 개체 `arrayObj`합니다.  
  
 `slice` 메서드 복사 까지의 점을 포함 하지 않고, 가리키는 요소 `end`합니다. 경우 `start` 가 음수 이면 것으로 간주 됩니다 `length`  +  `start`여기서 `length` 배열의 길이입니다. 경우 `end` 가 음수 이면 것으로 간주 됩니다 `length`  +  `end` 여기서 `length` 배열의 길이입니다. `end`를 생략하면 `arrayObj`의 끝까지 추출이 계속됩니다. 경우 `end` 앞에 오는 `start`, 요소가 없는 새 배열에 복사 됩니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 `slice` 메서드를 사용하는 방법을 보여 줍니다. 마지막 요소를 제외한 모든 첫 번째 예에서 `myArray` 에 복사 `newArray`합니다. 두 번째 예에서 마지막 두 개의 요소만 `myArray` 에 복사 `newArray`합니다.  
  
```JavaScript  
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
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [slice 메서드 (String)](../../javascript/reference/slice-method-string-javascript.md)   
 [String 개체](../../javascript/reference/string-object-javascript.md)