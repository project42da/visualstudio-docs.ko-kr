---
title: "ArrayBuffer 개체 | Microsoft Docs"
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
ms.assetid: 9fda1261-f450-493b-b3db-ecfa9ca93cd7
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c253d63d12a4a5e71d1661aae560b74debecdd62
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="arraybuffer-object"></a>ArrayBuffer 개체
다른 형식화된 배열용으로 데이터를 저장하는 데 사용되는 이진 데이터의 원시 버퍼를 나타냅니다. `ArrayBuffers`읽거나를 직접 쓸 수 없는 형식화 된 배열에 전달 될 수 있지만 또는 [DataView 개체](../../javascript/reference/dataview-object.md) 필요에 따라 원시 버퍼를 해석 하 합니다.  
  
 형식화 된 배열에 대 한 자세한 내용은 참조 [형식화 된 배열](../../javascript/advanced/typed-arrays-javascript.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
  
arrayBuffer = new ArrayBuffer(length);  
```  
  
## <a name="parameters"></a>매개 변수  
 `arrayBuffer`  
 필수 요소. `ArrayBuffer` 개체가 할당되는 변수 이름입니다.  
  
 `length`  
 버퍼의 길이입니다. Arraybuffer의 콘텐츠는 0으로 초기화됩니다. 요청된 바이트 수를 할당할 수 없으면 예외가 발생합니다.  
  
## <a name="properties"></a>속성  
 다음 표에서는 `ArrayBuffer` 개체의 속성을 보여 줍니다.  
  
|속성|설명|  
|--------------|-----------------|  
|[byteLength 속성](../../javascript/reference/bytelength-property-arraybuffer.md)|읽기 전용입니다. ArrayBuffer의 길이(바이트)입니다.|  
  
## <a name="functions"></a>함수  
 다음 표에서는 `ArrayBuffer` 개체의 함수를 보여줍니다.  
  
|속성|설명|  
|--------------|-----------------|  
|[ArrayBuffer.isView 함수](../../javascript/reference/arraybuffer-isview-function-arraybuffer.md)|개체에서 버퍼 뷰를 제공하는지 여부를 결정합니다.|  
  
## <a name="methods"></a>메서드  
 다음 표에서는 `ArrayBuffer` 개체의 메서드를 보여 줍니다.  
  
|속성|설명|  
|--------------|-----------------|  
|[slice 메서드](../../javascript/reference/slice-method-arraybuffer.md)|`ArrayBuffer`의 한 섹션을 반환합니다.|  
  
## <a name="example"></a>예제  
 ArrayBuffer 개체를 사용 하 여에서 가져온 이진 데이터를 처리 하는 방법을 보여 주는 다음 예제는 [XMLHttpRequest](http://msdn.microsoft.com/library/ie/ms535874\(v=vs.85\).aspx)합니다. 사용할 수는 [DataView 개체](../../javascript/reference/dataview-object.md) 개별 값을 가져옵니다.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Int32Array(buffer.byteLength / 4);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getInt32(i * 4);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="remarks"></a>설명  
 사용에 대 한 자세한 내용은 `XmlHttpRequest`, 참조 [XMLHttpRequest enhancements](http://msdn.microsoft.com/en-us/be09137c-6546-441b-b953-dcbf72b77069)합니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]