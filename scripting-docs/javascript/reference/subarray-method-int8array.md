---
title: "subarray 메서드 (Int8Array) | Microsoft Docs"
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
ms.assetid: 46271ed6-a3c3-41fb-bd6f-81efa9e8dedc
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e32c3a0da7e3173273eb40bf52bb6583bd77df51
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="subarray-method-int8array"></a>subarray 메서드(Int8Array)
시작 요소를 포함하고 끝 요소를 제외하여 참조하는 이 배열에 대한 ArrayBuffer 스토어의 새로운 Int8Array 뷰를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
var newInt8Array = int8Array.subset(begin, end);  
```  
  
## <a name="parameters"></a>매개 변수  
 `newInt8Array`  
 이 메서드에서 반환된 하위 배열입니다.  
  
 `begin`  
 배열의 시작 인덱스입니다.  
  
 `end`  
 배열의 끝 인덱스입니다. 이것은 포함되지 않습니다.  
  
## <a name="remarks"></a>설명  
 시작 또는 끝이 음수인 경우 시작과 반대인 배열 끝의 인덱스를 참조합니다. 끝이 지정되지 않은 경우 하위 배열에는 TypedArray의 처음부터 끝까지 모든 요소가 포함됩니다. 시작 및 끝 값에서 지정한 범위는 현재 배열의 유효한 인덱스 범위로 제한됩니다. 새 TypedArray의 계산된 길이가 음수이면 0으로 제한됩니다. 반환된 TypedArray는 이 메서드가 호출된 배열과 같은 형식이 됩니다.  
  
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
            var dataView = new DataView(buffer);  
            var intArr = new Int8Array(buffer.byteLength);  
            var subArr = intArr.subarray(0, 2);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]