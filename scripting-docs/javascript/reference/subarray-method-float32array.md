---
title: "subarray 메서드(Float32Array) | Microsoft Docs"
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
ms.assetid: 97aa27c0-d650-411e-b929-dd9c4a2ae9a5
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# subarray 메서드(Float32Array)
이 배열에 대한 [ArrayBuffer 개체](../../javascript/reference/arraybuffer-object.md) 저장소의 새 Float32Array 뷰를 가져오고 하위 배열의 첫 번째 및 마지막 멤버를 지정합니다.  
  
## 구문  
  
```javascript  
var newFloat32Array = float32Array.subarray(begin, end);  
```  
  
## 매개 변수  
 `newFloat32Array`  
 이 메서드에서 반환된 하위 배열입니다.  
  
 `begin`  
 배열의 시작 인덱스입니다.  
  
 `end`  
 배열의 끝 인덱스입니다.  
  
## 설명  
 `begin` 또는 `end`가 음수인 경우 시작과 반대인 배열 끝의 인덱스를 참조합니다.  `end`가 지정되지 않은 경우 하위 배열에는 TypedArray의 `begin`부터 형식화된 배열의 끝까지 모든 요소가 포함됩니다.  `begin` 및 `end` 값에서 지정한 범위는 현재 배열의 유효한 인덱스 범위로 제한됩니다.  새 형식화된 배열의 계산된 길이가 음수이면 0으로 제한됩니다.  반환된 배열은 이 메서드가 호출된 배열과 같은 형식입니다.  
  
## 예제  
 다음 예제에서는 배열의 첫 요소로 시작되는 세 개 요소 길이의 하위 배열을 가져오는 방법을 보여 줍니다.  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var floatArr = new Float32Array(buffer.byteLength / 4);  
            var subArr = floatArr.subarray(0, 2);  
        }  
    }  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]