---
title: "byteOffset 속성 (DataView) | Microsoft Docs"
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
ms.assetid: 3b3e68bc-1476-4a32-a18d-6efa375bce0f
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f7cfc829f9821dbf4eb440071b9c1971e8c4e882
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="byteoffset-property-dataview"></a>byteOffset 속성(DataView)
읽기 전용입니다. 이 보기를 생성 시 고정 된 바이트 단위로 ArrayBuffer의 시작 부분부터 오프셋입니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
var arrayOffset = dataView.byteOffset;  
```  
  
## <a name="example"></a>예제  
 다음 예제에 DataView의 길이 가져오는 방법을 보여 줍니다.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            alert(dataView.byteOffset)  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]