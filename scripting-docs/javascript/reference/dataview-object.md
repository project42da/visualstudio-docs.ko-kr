---
title: "DataView 개체 | Microsoft Docs"
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
ms.assetid: 250ec067-7505-4ee0-82ab-bfd3c2820afa
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 370ee1afbdf7fe1d87843c4979833d54a575a4fd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="dataview-object"></a>DataView 개체
DataView 개체를 읽고 ArrayBuffer의 임의 위치에 여러 종류의 이진 데이터를 쓸 사용할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dataView = new DataView(buffer, byteOffset, byteLength);  
```  
  
## <a name="parameters"></a>매개 변수  
 `dataView`  
 필수 요소. 변수 이름은 **DataView** 개체를 할당 합니다.  
  
 `buffer`  
 DataView가 나타내는 ArrayBuffer입니다.  
  
 `byteOffset`  
 선택 사항입니다. DataView를 시작할 버퍼의 시작 부분부터 바이트 오프셋을 지정 합니다.  
  
 `byteLength`  
 선택 사항입니다. DataView를 나타내야 하는 버퍼의 섹션 길이 바이트 단위로 지정 합니다.  
  
## <a name="remarks"></a>설명  
 ByteOffset와 byteLength 둘 다 생략 하면 DataView ArrayBuffer 범위 전체에 걸쳐 있습니다. ByteLength는 생략 된 경우 DataView ArrayBuffer 끝날 때까지 주어진된 byteOffset에서 확장 됩니다. 주어진된 byteOffset 및 byteLength ArrayBuffer의 끝을 넘어 영역을 참조 하는 경우 예외가 발생 합니다.  
  
## <a name="properties"></a>속성  
 다음 표에서는 `DataView` 개체의 속성을 보여 줍니다.  
  
|속성|설명|  
|--------------|-----------------|  
|[buffer 속성](../../javascript/reference/buffer-property-dataview.md)|읽기 전용입니다. 이 보기에서 참조 되는 ArrayBuffer를 가져옵니다.|  
|[byteLength 속성](../../javascript/reference/bytelength-property-dataview.md)|읽기 전용입니다. ArrayBuffer의 시작 부분부터 생성 시 고정된 이 뷰의 길이(바이트)입니다.|  
|[byteOffset 속성](../../javascript/reference/byteoffset-property-dataview.md)|읽기 전용입니다. 이 보기를 생성 시 고정 된 바이트 단위로 ArrayBuffer의 시작 부분부터 오프셋입니다.|  
  
## <a name="methods"></a>메서드  
 다음 표에서는 `DataView` 개체의 메서드를 보여 줍니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[getInt8 메서드](../../javascript/reference/getint8-method-dataview.md)|보기의 시작 부분부터 지정 된 바이트 오프셋에서 Int8 값을 가져옵니다.|  
|[getUint8 메서드(DataView)](../../javascript/reference/getuint8-method-dataview.md)|보기의 시작 부분부터 지정 된 바이트 오프셋에서 Uint8 값을 가져옵니다.|  
|[getInt16 메서드(DataView)](../../javascript/reference/getint16-method-dataview.md)|보기의 시작 부분부터 지정 된 바이트 오프셋에서 Int16 값을 가져옵니다.|  
|[getUint16 메서드(DataView)](../../javascript/reference/getuint16-method-dataview.md)|보기의 시작 부분부터 지정 된 바이트 오프셋에서 Uint16 값을 가져옵니다.|  
|[getInt32 메서드(DataView)](../../javascript/reference/getint32-method-dataview.md)|보기의 시작 부분부터 지정 된 바이트 오프셋에 Int32 값을 가져옵니다.|  
|[getUint32 메서드(DataView)](../../javascript/reference/getuint32-method-dataview.md)|보기의 시작 부분부터 지정 된 바이트 오프셋에서 Uint32 값을 가져옵니다.|  
|[getFloat32 메서드(DataView)](../../javascript/reference/getfloat32-method-dataview.md)|보기의 시작 부분부터 지정 된 바이트 오프셋에서 Float32 값을 가져옵니다.|  
|[getFloat64 메서드(DataView)](../../javascript/reference/getfloat64-method-dataview.md)|보기의 시작 부분부터 지정 된 바이트 오프셋에서 Float64 값을 가져옵니다.|  
|[setInt8 메서드(DataView)](../../javascript/reference/setint8-method-dataview.md)|보기의 시작 부분부터 지정 된 바이트 오프셋에 Int8 값을 저장 합니다.|  
|[setUint8 메서드(DataView)](../../javascript/reference/setuint8-method-dataview.md)|보기의 시작 부분부터 지정 된 바이트 오프셋에 Uint8 값을 저장 합니다.|  
|[setInt16 메서드(DataView)](../../javascript/reference/setint16-method-dataview.md)|보기의 시작 부분부터 지정 된 바이트 오프셋에 Int16 값을 저장 합니다.|  
|[setUint16 메서드(DataView)](../../javascript/reference/setuint16-method-dataview.md)|보기의 시작 부분부터 지정 된 바이트 오프셋에 Uint16 값을 저장 합니다.|  
|[setInt32 메서드(DataView)](../../javascript/reference/setint32-method-dataview.md)|보기의 시작 부분부터 지정 된 바이트 오프셋에 Int32 값을 저장 합니다.|  
|[setUint32 메서드(DataView)](../../javascript/reference/setuint32-method-dataview.md)|보기의 시작 부분부터 지정 된 바이트 오프셋에는 Uint32 값을 저장 합니다.|  
|[setFloat32 메서드(DataView)](../../javascript/reference/setfloat32-method-dataview.md)|보기의 시작 부분부터 지정 된 바이트 오프셋에 Float32 값을 저장 합니다.|  
|[setFloat64 메서드(DataView)](../../javascript/reference/setfloat64-method-dataview.md)|보기의 시작 부분부터 지정 된 바이트 오프셋에 Float64 값을 저장 합니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 DataView 개체를 사용 하 여 XmlHttpRequest에서 가져온 이진 데이터를 처리 하는 방법을 보여 줍니다.  
  
```JavaScript  
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
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]