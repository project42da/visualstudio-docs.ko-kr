---
title: "BYTES_PER_ELEMENT 상수(Uint8ClampedArray) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: f9fb2a10-9faf-4534-9183-dad2984e74ff
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# BYTES_PER_ELEMENT 상수(Uint8ClampedArray)
배열에서 각 요소의 크기\(바이트\)입니다.  
  
## 구문  
  
```javascript  
var arraySize = uint8ClampedArray.BYTES_PER_ELEMENT;  
```  
  
## 예제  
 다음 예제에서는 배열 요소의 크기를 가져오는 방법을 보여줍니다.  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Uint8ClampedArray(buffer.byteLength);  
            alert(intArr.BYTES_PER_ELEMENT);  
        }  
    }  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## 참고 항목  
 [Uint8ClampedArray 개체](../../javascript/reference/uint8clampedarray-object-javascript.md)