---
title: "buffer 속성 (Float32Array) | Microsoft Docs"
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
ms.assetid: 07b341ae-f83b-44ea-ad84-d5736eb51ec4
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 07f3039d931e14e0b6964146a2c22771b143437e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="buffer-property-float32array"></a>buffer 속성(Float32Array)
읽기 전용입니다. 이 배열에서 참조되는 ArrayBuffer를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
var arrayBuffer = float32Array.buffer;  
```  
  
## <a name="example"></a>예제  
 다음 예에서는 배열의 ArrayBuffer를 가져오는 방법을 보여 줍니다.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var floatArr = new Float32Array(buffer.byteLength / 4);  
            alert(floatArr.buffer.byteLength);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]