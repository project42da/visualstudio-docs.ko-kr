---
title: "Float32Array 개체 | Microsoft Docs"
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
ms.assetid: 4b29456a-1488-4006-ae66-5bf4c05003b1
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# Float32Array 개체
32비트 float 값에 대해 형식화된 배열입니다.  콘텐츠가 0으로 초기화됩니다.  요청된 바이트 수를 할당할 수 없으면 예외가 발생합니다.  
  
## 구문  
  
```  
  
float32Array = new Float32Array( length ); float32Array = new Float32Array( array ); float32Array = new Float32Array( buffer, byteOffset, length);  
```  
  
## 매개 변수  
 `float32Array`  
 필수 요소.  **Float32Array** 개체가 할당된 변수 이름입니다.  
  
 `length`  
 배열에 있는 요소의 수를 지정합니다.  
  
 `array`  
 이 배열에 포함된 배열\(또는 형식화된 배열\)입니다.  콘텐츠가 각 요소가 Float32 형식으로 변환된 주어진 배열 또는 형식화된 배열의 콘텐츠로 초기화됩니다.  
  
 `buffer`  
 Float32Array가 나타내는 ArrayBuffer입니다.  
  
 `byteOffset`  
 선택 사항입니다.  버퍼의 시작 지점에서 Float32Array를 시작할 오프셋\(바이트\)을 지정합니다.  
  
 `length`  
 배열의 요소 수입니다.  
  
## 상수  
 다음 표에서는 `Float32Array` 개체의 상수를 보여줍니다.  
  
|상수|설명|  
|--------|--------|  
|[BYTES\_PER\_ELEMENT 상수](../../javascript/reference/bytes-per-element-constant-float32array.md)|배열에서 각 요소의 크기\(바이트\)입니다.|  
  
## 속성  
 다음 표에서는 `Float32Array` 개체의 상수를 보여줍니다.  
  
|속성|설명|  
|--------|--------|  
|[buffer 속성](../../javascript/reference/buffer-property-float32array.md)|읽기 전용입니다.  이 배열에서 참조되는 ArrayBuffer를 가져옵니다.|  
|[byteLength 속성](../../javascript/reference/bytelength-property-float32array.md)|읽기 전용입니다.  ArrayBuffer의 시작 부분부터 생성 시 고정된 이 배열의 길이\(바이트\)입니다.|  
|[byteOffset 속성](../../javascript/reference/byteoffset-property-float32array.md)|읽기 전용입니다.  ArrayBuffer의 시작 부분부터 생성 시 고정된 이 배열의 오프셋\(바이트\)입니다.|  
|[length 속성](../../javascript/reference/length-property-float32array.md)|배열의 길이입니다.|  
|||  
  
## 메서드  
 다음 표에서는 `Float32Array` 개체의 메서드를 보여 줍니다.  
  
|메서드|설명|  
|---------|--------|  
|[get 메서드](../../javascript/reference/get-method-float32array.md)|생략 가능.  지정한 인덱스에 있는 요소를 가져옵니다.|  
|[set 메서드\(Float32Array\)](../../javascript/reference/set-method-float32array.md)|값 또는 값의 배열을 설정합니다.|  
|[subarray 메서드\(Float32Array\)](../../javascript/reference/subarray-method-float32array.md)|이 배열에 대한 ArrayBuffer 저장소의 새 Float32Array 뷰를 가져옵니다.|  
  
## 예제  
 다음 예제에서는 Float32Array 개체를 사용하여 XmlHttpRequest에서 가져온 이진 데이터를 처리하는 방법을 보여줍니다.  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Float32Array(buffer.byteLength / 4);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getFloat32(i * 4);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]