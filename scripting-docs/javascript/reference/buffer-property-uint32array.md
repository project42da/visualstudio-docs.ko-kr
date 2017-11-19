---
title: "buffer 속성 (Uint32Array) | Microsoft Docs"
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
ms.assetid: 7bd098c5-25c4-4e45-aeb2-95cc8f2325dc
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 579b60bb31550713f6c3e6bcafd7b57c66749ca7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="buffer-property-uint32array"></a>buffer 속성(Uint32Array)
읽기 전용입니다. 이 배열에서 참조되는 ArrayBuffer를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
var arrayBuffer = uint32Array.buffer;  
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
            var intArr = new Uint32Array(buffer.byteLength / 4);  
            alert(intArr.buffer.byteLength);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]