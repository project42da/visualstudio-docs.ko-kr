---
title: "slice 메서드(ArrayBuffer) | Microsoft Docs"
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
ms.assetid: 2dcc51ff-f444-4d51-80ba-3bcd845ba0ae
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# slice 메서드(ArrayBuffer)
[ArrayBuffer](../../javascript/reference/arraybuffer-object.md)의 한 섹션을 반환합니다.  
  
## 구문  
  
```  
arrayBufferObj.slice(start, [end])   
```  
  
## 매개 변수  
 `arrayBufferObj`  
 필수 요소.  복사할 섹션이 있는 [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) 개체입니다.  
  
 `start`  
 필수 요소.  복사할 섹션의 시작 바이트 인덱스입니다.  
  
 `end`  
 선택 사항입니다.  복사할 섹션의 끝 바이트 인덱스입니다.  
  
## 설명  
 `slice` 메서드는 지정한 `arrayBufferObj` 부분이 포함된 [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) 개체를 반환합니다.  
  
 `slice` 메서드는 `end`로 지정된 바이트까지\(해당 바이트는 포함하지 않음\) 복사합니다.  `start` 또는 `end`가 음수이면 지정된 인덱스는 각각 `length` \+ `start` 또는 `end`로 처리됩니다. 여기서 `length`는 [ArrayBuffer](../../javascript/reference/arraybuffer-object.md)의 길이입니다.  `end`를 생략하면 `arrayBufferObj`의 끝까지 추출이 계속됩니다.  `end`가 `start`보다 앞에 나오면 새 [ArrayBuffer](../../javascript/reference/arraybuffer-object.md)로 바이트가 복사되지 않습니다.  
  
## 예제  
 다음 예에서는 `slice` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer1 = req.response;  
            var buffer2 = buffer1.slice(40, 48);  
            var dataview = new DataView(buffer2);  
            var ints = new Int32Array(buffer2.byteLength / 4);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getInt32(i * 4);  
            }  
        alert(ints[1]);  
        }  
    }  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## 참고 항목  
 [ArrayBuffer 개체](../../javascript/reference/arraybuffer-object.md)