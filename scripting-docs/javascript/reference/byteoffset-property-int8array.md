---
title: "byteOffset 속성 (Int8Array) | Microsoft Docs"
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
ms.assetid: b155bf97-d567-4921-8edd-dbca0d84b6cf
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 66ef19bafd3f33461ce1f632e735400e8acf10c6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="byteoffset-property-int8array"></a>byteOffset 속성(Int8Array)
읽기 전용입니다. ArrayBuffer의 시작 부분부터 생성 시 고정된 이 배열의 오프셋(바이트)입니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
var arrayOffset = int8Array.byteOffset;  
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
            var intArr = new Int8Array(buffer.byteLength);  
            alert(intArr.byteOffset);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]