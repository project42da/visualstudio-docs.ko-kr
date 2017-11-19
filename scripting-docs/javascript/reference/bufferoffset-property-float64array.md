---
title: "bufferOffset 속성 (Float64Array) | Microsoft Docs"
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
ms.assetid: 9b566ec9-97d1-4a54-96cd-c1608f0ed330
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a2d64af7d1f7aeb9f4f42ee1854c5a6a93ad5505
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="bufferoffset-property-float64array"></a>bufferOffset 속성(Float64Array)
읽기 전용입니다. ArrayBuffer의 시작 부분부터 생성 시 고정된 이 배열의 오프셋(바이트)입니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
var arrayOffset = float64Array.byteOffset;  
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
            var floatArr = new Float64Array(buffer.byteLength / 8);  
            alert(floatArr.byteOffset);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]