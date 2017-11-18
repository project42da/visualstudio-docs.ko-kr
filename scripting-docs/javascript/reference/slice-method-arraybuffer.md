---
title: "slice 메서드 (ArrayBuffer) | Microsoft Docs"
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
ms.assetid: 2dcc51ff-f444-4d51-80ba-3bcd845ba0ae
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 25fc10a02b4a3422a6720ad91c8bba29906da0e5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="slice-method-arraybuffer"></a>slice 메서드(ArrayBuffer)
부분을 반환 된 [ArrayBuffer](../../javascript/reference/arraybuffer-object.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
arrayBufferObj.slice(start, [end])   
```  
  
## <a name="parameters"></a>매개 변수  
 `arrayBufferObj`  
 필수 요소. [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) 개체 섹션에서 복사 됩니다.  
  
 `start`  
 필수 요소. 복사할 섹션의 시작 바이트 인덱스입니다.  
  
 `end`  
 선택 사항입니다. 복사할 섹션의 끝 바이트 인덱스입니다.  
  
## <a name="remarks"></a>설명  
 `slice` 메서드가 반환 되는 [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) 의 지정된 된 부분을 포함 하는 개체 `arrayBufferObj`합니다.  
  
 `slice` 메서드는 `end`로 지정된 바이트까지(해당 바이트는 포함하지 않음) 복사합니다. 경우 `start` 또는 `end` 가 음수 이면 지정된 된 인덱스로 처리 됩니다 `length`  +  `start` 또는 `end`각각 여기서 `length` 의 길이 [ArrayBuffer](../../javascript/reference/arraybuffer-object.md). `end`를 생략하면 `arrayBufferObj`의 끝까지 추출이 계속됩니다. 경우 `end` 앞에 오는 `start`, 새 없습니다 바이트가 복사 [ArrayBuffer](../../javascript/reference/arraybuffer-object.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 `slice` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer1 = req.response;  
            var buffer2 = buffer1.slice(40, 48);  
            var dataview = new DataView(buffer2);  
            var ints = new Int32Array(buffer2.byteLength / 4);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getInt32(i * 4);  
            }  
        alert(ints[1]);  
        }  
    }  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ArrayBuffer 개체](../../javascript/reference/arraybuffer-object.md)