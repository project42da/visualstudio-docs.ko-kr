---
title: "byteLength 속성 (Int32Array) | Microsoft Docs"
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
ms.assetid: 9d09754d-d08b-434a-a9c4-46700fa49377
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b9e8df3807fc1fd5cf5397094c6638cbc24b03df
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="bytelength-property-int32array"></a>byteLength 속성(Int32Array)
읽기 전용입니다. ArrayBuffer의 시작 부분부터 생성 시 고정된 이 배열의 길이(바이트)입니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
var arrayByteLength = int32Array.byteLength;  
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
            var intArr = new Int32Array(buffer.byteLength / 4);  
            alert(intArr.byteLength);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]