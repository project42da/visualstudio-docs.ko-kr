---
title: "get 메서드 (Float32Array) | Microsoft Docs"
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
ms.assetid: f859481c-0bb8-43d3-9d54-38d303e44397
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ea17b3d26a1f192843a2fb9d2d87f62fe26fceff
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="get-method-float32array"></a>get 메서드(Float32Array)
생략 가능. 지정한 인덱스에 있는 요소를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
var value = float32Array.get(index);  
```  
  
## <a name="parameters"></a>매개 변수  
 `value`  
 이 메서드에서 반환된 값입니다.  
  
 `index`  
 배열의 요소를 가져올 인덱스입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 배열의 첫 번째 요소를 가져오는 방법을 보여줍니다.  
  
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
            var element = floatArr.getFloat32(0);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]