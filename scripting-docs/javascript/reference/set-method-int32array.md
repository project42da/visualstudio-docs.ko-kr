---
title: "set 메서드 (Int32Array) | Microsoft Docs"
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
ms.assetid: c0716454-88dc-43d5-8ce9-f8fdc91da4c5
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 033c2ba996b5754ec15eb97d9926f20a88c0dc6e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="set-method-int32array"></a>set 메서드(Int32Array)
값 또는 값의 배열을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
Int32Array.set(index, value);  
int32Array.set(array, offset);  
  
```  
  
## <a name="parameters"></a>매개 변수  
 `index`  
 설정할 위치의 인덱스입니다.  
  
 `value`  
 설정할 값입니다.  
  
 `array`  
 설정할 값의 형식화되거나 형식화되지 않은 배열입니다.  
  
 `offset`  
 값을 기록할 현재 배열의 인덱스입니다.  
  
## <a name="remarks"></a>설명  
 입력 배열이 TypedArray인 경우 두 가지 배열은 동일한 기본 ArrayBuffer를 사용할 수 있습니다. 이 경우 모든 데이터가 배열 중 하나와 겹치지 않는 임시 버퍼로 먼저 복사된 다음 임시 버퍼의 데이터가 현재 배열로 복사되는 것처럼 값이 설정됩니다.  
  
 오프셋과 지정된 배열의 길이가 현재 TypedArray 범위를 벗어나는 경우 예외가 발생합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 배열의 첫 번째 요소를 설정하는 방법을 보여줍니다.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Int32Array(buffer.byteLength / 4);  
            intArr.set(0, 9);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]