---
title: "subarray 메서드(Uint8ClampedArray) | Microsoft Docs"
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
ms.assetid: 309ed9e8-5805-47ab-b3ed-501cae1323dd
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# subarray 메서드(Uint8ClampedArray)
이 배열에 대한 [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) 저장소의 새 [Uint8ClampedArray](../../javascript/reference/uint8array-object.md) 뷰를 가져오고 하위 배열의 첫 번째 및 마지막 멤버를 지정합니다.  
  
## 구문  
  
```javascript  
var newUint8ClampedArray = uint8ClampedArray.subarray(begin, end);  
```  
  
## 매개 변수  
 `newUint8ClampedArray`  
 필수.  이 메서드에서 반환된 하위 배열입니다.  
  
 `begin`  
 선택 사항입니다.  배열의 시작 인덱스입니다.  
  
 `end`  
 선택 사항입니다.  배열의 끝 인덱스입니다.  이것은 포함되지 않습니다.  
  
## 설명  
 `begin` 또는 `end`가 음수인 경우 시작과 반대인 배열 끝의 인덱스를 참조합니다.  `end`가 지정되지 않은 경우 하위 배열에는 `begin`부터 형식화된 배열의 끝까지 모든 요소가 포함됩니다.  `begin` 및 `end` 값으로 지정되는 범위는 현재 배열의 유효한 인덱스 범위로 제한됩니다.  새 형식화된 배열의 계산된 길이가 음수이면 0으로 제한됩니다.  반환된 배열에는 이 메서드가 호출된 배열과 같은 유형이 있습니다.  
  
## 예제  
 다음 예제에서는 배열의 첫 요소로 시작되는 두 개 요소 길이의 하위 배열을 가져오는 방법을 보여줍니다.  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var intArr = new Uint8ClampedArray(buffer.byteLength);  
            var subArr = intArr.subarray(0, 2);  
        }  
    }  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## 참고 항목  
 [Uint8Array 개체](../../javascript/reference/uint8array-object.md)   
 [ArrayBuffer 개체](../../javascript/reference/arraybuffer-object.md)   
 [Uint8ClampedArray 개체](../../javascript/reference/uint8clampedarray-object-javascript.md)