---
title: "byteLength 속성 (ArrayBuffer) | Microsoft Docs"
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
ms.assetid: c158fa59-d006-4842-9d06-0fd8e630ea31
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5f576eb85652a7c250e0f446f4082dd6207e8fb2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="bytelength-property-arraybuffer"></a>byteLength 속성(ArrayBuffer)
읽기 전용입니다. ArrayBuffer의 길이(바이트)입니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
var arrayLength = arrayBuffer.byteLength;  
```  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예제  
 다음 예에서는 ArrayBuffer의 바이트 길이 가져오는 방법을 보여 줍니다.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
  
        alert(buffer.byteLength);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]