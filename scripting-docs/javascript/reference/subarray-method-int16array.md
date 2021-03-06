---
title: "subarray 메서드 (Int16Array) | Microsoft Docs"
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
ms.assetid: 8a7437c2-8c4e-41eb-a3d5-ec4f7399b81d
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9b5407787f07c36c88da224b1addcda02c486e7a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="subarray-method-int16array"></a>subarray 메서드(Int16Array)
새 Int16Array 뷰를 가져옵니다는 [ArrayBuffer 개체](../../javascript/reference/arraybuffer-object.md) 고 하위 배열의 첫 번째 및 마지막 멤버를 지정 하는이 배열에 대 한 저장소입니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
var newInt16Array = int16Array.subarray(begin, end);  
```  
  
## <a name="parameters"></a>매개 변수  
 `newInt16Array`  
 이 메서드에서 반환된 하위 배열입니다.  
  
 `begin`  
 배열의 시작 인덱스입니다.  
  
 `end`  
 배열의 끝 인덱스입니다. 이것은 포함되지 않습니다.  
  
## <a name="remarks"></a>설명  
 `begin` 또는 `end`가 음수인 경우 시작과 반대인 배열 끝의 인덱스를 참조합니다. `end`가 지정되지 않은 경우 하위 배열에는 형식화된 배열의 처음부터 끝까지 모든 요소가 포함됩니다. `begin` 및 `end` 값으로 지정되는 범위는 현재 배열의 유효한 인덱스 범위로 제한됩니다. 새 형식화된 배열의 계산된 길이가 음수이면 0으로 제한됩니다. 반환된 배열은 이 메서드가 호출된 배열과 같은 형식입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 배열의 첫 요소로 시작되는 두 개 요소 길이의 하위 배열을 가져오는 방법을 보여줍니다.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var intArr = new Int16Array(buffer.byteLength / 2);  
            var subArr = intArr.subarray(0, 2);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]