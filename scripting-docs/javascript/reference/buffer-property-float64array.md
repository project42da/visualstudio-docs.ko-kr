---
title: "buffer 속성 (Float64Array) | Microsoft Docs"
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
ms.assetid: 61bd0b28-6608-458c-9833-203d063081ec
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d6e7bd88701e8dafb4091d6d248493931fd2eff2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="buffer-property-float64array"></a>buffer 속성(Float64Array)
읽기 전용입니다. 이 배열에서 참조되는 ArrayBuffer를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
var arrayBuffer = float64Array.buffer;  
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
            var floatArr = new Float64Array(buffer.byteLength / 8);  
            alert(floatArr.buffer.byteLength);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]