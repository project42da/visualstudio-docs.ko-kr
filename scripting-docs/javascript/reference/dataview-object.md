---
title: "DataView 개체 | Microsoft Docs"
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
ms.assetid: 250ec067-7505-4ee0-82ab-bfd3c2820afa
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# DataView 개체
DataView 개체를 사용하면 ArrayBuffer의 임의 위치에서 여러 종류의 이진 데이터를 읽고 쓸 수 있습니다.  
  
## 구문  
  
```  
  
dataView = new DataView(buffer, byteOffset, byteLength);  
```  
  
## 매개 변수  
 `dataView`  
 필수 요소.  **DataView** 개체가 할당된 변수 이름입니다.  
  
 `buffer`  
 DataView가 나타내는 ArrayBuffer입니다.  
  
 `byteOffset`  
 선택 사항입니다.  버퍼의 시작 지점에서부터 DataView를 시작할 오프셋\(바이트\)을 지정합니다.  
  
 `byteLength`  
 선택 사항입니다.  버퍼의 섹션에서 DataView가 나타낼 길이\(바이트\)를 지정합니다.  
  
## 설명  
 byteOffset 및 byteLength를 모두 생략한 경우 DataView가 전체 ArrayBuffer 범위에 걸쳐집니다.  byteLength를 모두 생략한 경우 DataView가 지정된 byteOffset으로부터 ArrayBuffer의 끝까지 확장됩니다.  지정된 byteOffset 및 byteLength가 ArrayBuffer의 끝을 넘는 영역을 참조할 경우 예외가 발생합니다.  
  
## 속성  
 다음 표에서는 `DataView` 개체의 속성을 보여 줍니다.  
  
|속성|설명|  
|--------|--------|  
|[buffer 속성](../../javascript/reference/buffer-property-dataview.md)|읽기 전용입니다.  이 뷰에서 참조되는 ArrayBuffer를 가져옵니다.|  
|[byteLength 속성](../../javascript/reference/bytelength-property-dataview.md)|읽기 전용입니다.  ArrayBuffer의 시작 부분부터 생성 시 고정된 대로의 이 뷰의 길이\(바이트\)입니다.|  
|[byteOffset 속성](../../javascript/reference/byteoffset-property-dataview.md)|읽기 전용입니다.  ArrayBuffer의 시작 부분부터 생성 시 고정된 대로의 이 뷰의 오프셋\(바이트\)입니다.|  
  
## 메서드  
 다음 표에서는 `DataView` 개체의 메서드를 보여 줍니다.  
  
|방법|설명|  
|--------|--------|  
|[getInt8 메서드](../../javascript/reference/getint8-method-dataview.md)|뷰의 시작 지점에서 지정된 오프셋 바이트 수만큼 Int8 값을 가져옵니다.|  
|[getUint8 메서드\(DataView\)](../../javascript/reference/getuint8-method-dataview.md)|뷰의 시작 지점에서 지정된 오프셋 바이트 수만큼 Uint8 값을 가져옵니다.|  
|[getInt16 메서드\(DataView\)](../../javascript/reference/getint16-method-dataview.md)|뷰의 시작 지점에서 지정된 오프셋 바이트 수만큼 Int16 값을 가져옵니다.|  
|[getUint16 메서드\(DataView\)](../../javascript/reference/getuint16-method-dataview.md)|뷰의 시작 지점에서 지정된 오프셋 바이트 수만큼 Uint16 값을 가져옵니다.|  
|[getInt32 메서드\(DataView\)](../../javascript/reference/getint32-method-dataview.md)|뷰의 시작 지점에서 지정된 오프셋 바이트 수만큼 Int32 값을 가져옵니다.|  
|[getUint32 메서드\(DataView\)](../../javascript/reference/getuint32-method-dataview.md)|뷰의 시작 지점에서 지정된 오프셋 바이트 수만큼 Uint32 값을 가져옵니다.|  
|[getFloat32 메서드\(DataView\)](../../javascript/reference/getfloat32-method-dataview.md)|뷰의 시작 지점에서 지정된 오프셋 바이트 수만큼 Float32 값을 가져옵니다.|  
|[getFloat64 메서드\(DataView\)](../../javascript/reference/getfloat64-method-dataview.md)|뷰의 시작 지점에서 지정된 오프셋 바이트 수만큼 Float6 값을 가져옵니다.|  
|[setInt8 메서드\(DataView\)](../../javascript/reference/setint8-method-dataview.md)|뷰의 시작 지점에서 지정된 오프셋 바이트 수만큼 Int8 값을 저장합니다.|  
|[setUint8 메서드\(DataView\)](../../javascript/reference/setuint8-method-dataview.md)|뷰의 시작 지점에서 지정된 오프셋 바이트 수만큼 Uint8 값을 저장합니다.|  
|[setInt16 메서드\(DataView\)](../../javascript/reference/setint16-method-dataview.md)|뷰의 시작 지점에서 지정된 오프셋 바이트 수만큼 Int16 값을 저장합니다.|  
|[setUint16 메서드\(DataView\)](../../javascript/reference/setuint16-method-dataview.md)|뷰의 시작 지점에서 지정된 오프셋 바이트 수만큼 Uint16 값을 저장합니다.|  
|[setInt32 메서드\(DataView\)](../../javascript/reference/setint32-method-dataview.md)|뷰의 시작 지점에서 지정된 오프셋 바이트 수만큼 Int32 값을 저장합니다.|  
|[setUint32 메서드\(DataView\)](../../javascript/reference/setuint32-method-dataview.md)|뷰의 시작 지점에서 지정된 오프셋 바이트 수만큼 Uint32 값을 저장합니다.|  
|[setFloat32 메서드\(DataView\)](../../javascript/reference/setfloat32-method-dataview.md)|뷰의 시작 지점에서 지정된 오프셋 바이트 수만큼 Float32 값을 저장합니다.|  
|[setFloat64 메서드\(DataView\)](../../javascript/reference/setfloat64-method-dataview.md)|뷰의 시작 지점에서 지정된 오프셋 바이트 수만큼 Float64 값을 저장합니다.|  
  
## 예제  
 다음 예제에서는 DataView 개체를 사용하여 XmlHttpRequest에서 가져온 이진 데이터를 처리하는 방법을 보여 줍니다.  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var ints = new Int32Array(dataView.byteLength / 4);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getInt32(i * 4);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]