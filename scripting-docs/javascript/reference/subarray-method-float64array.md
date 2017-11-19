---
title: "subarray 메서드 (Float64Array) | Microsoft Docs"
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
ms.assetid: f3c24e1b-5fb2-49a1-8183-0fda33dbeaba
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 08f72854b9dc87394bdce2552d5d48ff4b1270f8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="subarray-method-float64array"></a>subarray 메서드(Float64Array)
새 Float64Array 뷰를 가져옵니다는 [ArrayBuffer 개체](../../javascript/reference/arraybuffer-object.md) 고 하위 배열의 첫 번째 및 마지막 멤버를 지정 하는이 배열에 대 한 저장소입니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
var newFloat64Array = float64Array.subarray(begin, end);  
```  
  
## <a name="parameters"></a>매개 변수  
 `newFloat64Array`  
 이 메서드에서 반환된 하위 배열입니다.  
  
 `begin`  
 배열의 시작 인덱스입니다.  
  
 `end`  
 배열의 끝 인덱스입니다.  
  
## <a name="remarks"></a>설명  
 `begin` 또는 `end`가 음수인 경우 시작과 반대인 배열 끝의 인덱스를 참조합니다. `end`가 지정되지 않은 경우 하위 배열에는 `begin`부터 형식화된 배열의 끝까지 모든 요소가 포함됩니다. `begin` 및 `end` 값으로 지정되는 범위는 현재 배열의 유효한 인덱스 범위로 제한됩니다. 새 형식화된 배열의 계산된 길이가 음수이면 0으로 제한됩니다. 반환된 배열은 이 메서드가 호출된 배열과 같은 형식입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 3 개 요소 배열의 첫 요소로 시작 길이의 하위 배열을 가져오는 방법을 보여 줍니다.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var floatArr = new Float64Array(buffer.byteLength / 8);  
            var subArr = floatArr.subarray(0, 2);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]