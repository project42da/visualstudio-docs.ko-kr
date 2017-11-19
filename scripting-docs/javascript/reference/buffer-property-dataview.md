---
title: "buffer 속성 (DataView) | Microsoft Docs"
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
ms.assetid: b69afc28-586e-4277-8cd6-b9d69a54fb55
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 83dae7c89ba4ae943d04efc92ca637e0d7447ec4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="buffer-property-dataview"></a>buffer 속성(DataView)
읽기 전용입니다. 이 보기에서 참조 되는 ArrayBuffer를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
var arrayBuffer = dataView.buffer;  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 기본 DataView ArrayBuffer의 길이 가져오는 방법을 보여 줍니다.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            alert(dataView.buffer.byteLength)  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]