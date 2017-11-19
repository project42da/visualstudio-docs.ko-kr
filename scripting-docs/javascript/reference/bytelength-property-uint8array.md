---
title: "byteLength 속성 (Uint8Array) | Microsoft Docs"
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
ms.assetid: 3a261c05-555e-4ecd-b946-2d56fdad0247
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 561dabb3da6381162c0d1c064c6ac8af085ec5ee
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="bytelength-property-uint8array"></a>byteLength 속성(Uint8Array)
읽기 전용입니다. ArrayBuffer의 시작 부분부터 생성 시 고정된 이 배열의 길이(바이트)입니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
var arrayByteLength = uint8Array.byteLength;  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 배열의 길이를 가져오는 방법을 보여줍니다.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Uint8Array(buffer.byteLength);  
            alert(intArr.byteLength);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]