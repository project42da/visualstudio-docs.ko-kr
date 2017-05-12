---
title: "subarray 메서드(Int16Array) | Microsoft Docs"
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
ms.assetid: 8a7437c2-8c4e-41eb-a3d5-ec4f7399b81d
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# subarray 메서드(Int16Array)
이 배열에 대한 [ArrayBuffer 개체](../../javascript/reference/arraybuffer-object.md) 저장소의 새 Int16Array 뷰를 가져오고 하위 배열의 첫 번째 및 마지막 멤버를 지정합니다.  
  
## 구문  
  
```javascript  
var newInt16Array = int16Array.subarray(begin, end);  
```  
  
## 매개 변수  
 `newInt16Array`  
 이 메서드에서 반환된 하위 배열입니다.  
  
 `begin`  
 배열의 시작 인덱스입니다.  
  
 `end`  
 배열의 끝 인덱스입니다.  이것은 포함되지 않습니다.  
  
## 설명  
 `begin` 또는 `end`가 음수인 경우 시작과 반대인 배열 끝의 인덱스를 참조합니다.  `end`가 지정되지 않은 경우 하위 배열에는 형식화된 배열의 처음부터 끝까지 모든 요소가 포함됩니다.  `begin` 및 `end` 값으로 지정되는 범위는 현재 배열의 유효한 인덱스 범위로 제한됩니다.  새 형식화된 배열의 계산된 길이가 음수이면 0으로 제한됩니다.  반환된 배열은 이 메서드가 호출된 배열과 같은 형식입니다.  
  
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
            var intArr = new Int16Array(buffer.byteLength / 2);  
            var subArr = intArr.subarray(0, 2);  
        }  
    }  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]