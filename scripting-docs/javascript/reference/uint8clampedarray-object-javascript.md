---
title: "Uint8ClampedArray 개체 (JavaScript) | Microsoft Docs"
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
ms.assetid: 0c5537f7-00b4-487a-8fba-ef032e67e7bd
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 51673eadc8eb905355bf136dc82b2f240462180a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="uint8clampedarray-object-javascript"></a>Uint8ClampedArray 개체(JavaScript)
값 범위가 0~255로 제한되는 8비트 부호 없는 정수의 형식화된 배열입니다. 콘텐츠가 0으로 초기화됩니다. 요청된 바이트 수를 할당할 수 없으면 예외가 throw됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      uint8ClampedArray = new Uint8ClampedArray( length );  
uint8ClampedArray = new Uint8ClampedArray( array );  
uint8ClampedArray = new Uint8ClampedArray( buffer, byteOffset, length);  
```  
  
## <a name="parameters"></a>매개 변수  
 `uint8ClampedArray`  
 필수 요소. `Uint8ClampedArray` 개체가 할당되는 변수 이름입니다.  
  
 `length`  
 선택 사항입니다. 배열의 요소 수입니다.  
  
 `array`  
 선택 사항입니다. 이 배열에 포함된 배열 또는 형식화된 배열입니다. 콘텐츠는 지정된 배열 또는 형식화된 배열의 콘텐츠로 초기화되며, 이때 각 요소가 `Uint8` 형식으로 변환됩니다.  
  
 `buffer`  
 선택 사항입니다. [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) 하는 `Uint8ClampedArray` 나타냅니다.  
  
 `byteOffset`  
 선택 사항입니다. 버퍼의 시작 지점에서 `Uint8ClampedArray`를 시작할 오프셋(바이트)입니다.  
  
 `length`  
 선택 사항입니다. 배열의 요소 수입니다.  
  
## <a name="remarks"></a>설명  
 `Uint8ClampedArray` 개체에는 0~255 사이의 값이 저장됩니다. 배열 멤버로 음수 값을 설정하면 해당 값에는 0이 설정됩니다. 255보다 큰 값을 설정하면 해당 값으로 255가 설정됩니다.  
  
 값에 `Uint8ClampedArray` 개체도 반올림 되는 가장 가까운 짝수 값, 호출 된 은행원의 반올림 합니다.  
  
## <a name="constants"></a>상수  
 다음 표에서는 `Uint8ClampedArray` 개체의 상수를 보여줍니다.  
  
|상수|설명|  
|--------------|-----------------|  
|[BYTES_PER_ELEMENT 상수](../../javascript/reference/bytes-per-element-constant-uint8clampedarray.md)|배열에서 각 요소의 크기(바이트)입니다.|  
  
## <a name="properties"></a>속성  
 다음 표에서는 `Uint8ClampedArray` 개체의 상수를 보여줍니다.  
  
|속성|설명|  
|--------------|-----------------|  
|[buffer 속성](../../javascript/reference/buffer-property-uint8clampedarray.md)|읽기 전용입니다. 가져옵니다는 [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) 이 배열에서 참조 하는 합니다.|  
|[byteLength 속성](../../javascript/reference/bytelength-property-uint8clampedarray.md)|읽기 전용입니다. 시작 부분부터이 배열의 길이 [ArrayBuffer](../../javascript/reference/arraybuffer-object.md), 생성 시 고정 된 바이트에서입니다.|  
|[byteOffset 속성](../../javascript/reference/byteoffset-property-uint8clampedarray.md)|읽기 전용입니다. 시작 부분부터이 배열의 오프셋 해당 [ArrayBuffer](../../javascript/reference/arraybuffer-object.md), 생성 시 고정 된 바이트에서입니다.|  
|[length 속성](../../javascript/reference/length-property-uint8clampedarray.md)|배열의 길이입니다.|  
  
## <a name="methods"></a>메서드  
 다음 표에서는 `Uint8ClampedArray` 개체의 메서드를 보여 줍니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[set 메서드](../../javascript/reference/set-method-uint8clampedarray.md)|값 또는 값의 배열을 설정합니다.|  
|[subarray 메서드](../../javascript/reference/subarray-method-uint8clampedarray.md)|새 가져옵니다 `Uint8ClampedArray` 볼 수는 [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) 의 하위 배열의 첫 번째 및 마지막 요소를 지정 하는이 배열에 대 한 저장소입니다.|  
  
## <a name="example"></a>예제  
 다음 예에서는 `Uint8ClampedArray` 개체를 사용하여 `XmlHttpRequest`에서 가져온 이진 데이터를 처리하는 방법을 보여 줍니다.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Uint8ClampedArray(buffer.byteLength);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getUint8(i);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="example"></a>예제  
 다음 예에서는 `Uint8ClampedArray`에서 값을 제한하는 방법을 보여 줍니다.  
  
```JavaScript  
var ints = new Uint8ClampedArray(2);  
ints[0] = -1;  // 0 will be assigned.  
ints[1] = 256; // 255 will be assigned.  
  
```  
  
## <a name="example"></a>예제  
 다음 예에서는 `Uint8ClampedArray`에서 값을 반올림하는 방법을 보여 줍니다.  
  
```  
var ints = new Uint8ClampedArray(4);  
ints[0] = 11.3; // 11 will be assigned (same as Int8Array).  
ints[1] = 11.8; // 12 will be assigned (same as Int8Array).  
ints[2] = 10.5; // 10 will be assigned (rounded to the nearest   
                // even value).  
ints[3] = 11.5; // 12 will be assigned (rounded to the nearest   
                // even value).  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Uint8Array 개체](../../javascript/reference/uint8array-object.md)   
 [ArrayBuffer 개체](../../javascript/reference/arraybuffer-object.md)
