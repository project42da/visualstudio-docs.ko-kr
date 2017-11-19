---
title: "byteOffset 속성 (Uint8ClampedArray) | Microsoft Docs"
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
ms.assetid: bfc22cf4-00e3-4e2c-8419-032b179aa8da
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7997c90f59796f519cdeb4cab3f88965539d460b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="byteoffset-property-uint8clampedarray"></a>byteOffset 속성(Uint8ClampedArray)
읽기 전용입니다. 시작 부분부터이 배열의 오프셋 해당 [ArrayBuffer](../../javascript/reference/arraybuffer-object.md), 생성 시 고정 된 바이트에서입니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
var arrayOffset = uint8ClampedArray.byteOffset;  
```  
  
## <a name="example"></a>예제  
 다음 예에서는 배열의 오프셋을 가져오는 방법을 보여 줍니다.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Uint8ClampedArray(buffer.byteLength);  
            alert(intArr.byteOffset);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ArrayBuffer 개체](../../javascript/reference/arraybuffer-object.md)   
 [Uint8ClampedArray 개체](../../javascript/reference/uint8clampedarray-object-javascript.md)