---
title: "형식화된 배열(JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: fa82c562-0ebf-4559-aecc-166e59f7fb64
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5fc3b29a4593e7c627a6e606242229e87fa5be54
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="typed-arrays-javascript"></a>형식화된 배열(JavaScript)
형식화된 배열을 사용하여 네트워크 프로토콜, 이진 파일 형식 및 원시 그래픽 버퍼와 같은 소스에서 이진 데이터를 처리할 수 있습니다. 형식화된 배열을 사용하여 잘 알려진 바이트 레이아웃을 통해 메모리 내 이진 데이터를 관리할 수도 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 [ArrayBuffer 개체](../../javascript/reference/arraybuffer-object.md)를 [XMLHttpRequest](http://msdn.microsoft.com/library/ie/ms535874\(v=vs.85\).aspx)의 응답으로 사용하는 방법을 보여 줍니다. [DataView 개체](../../javascript/reference/dataview-object.md)의 다양한 메서드를 사용하거나 바이트를 해당하는 형식화된 배열로 복사하여 응답에서 바이트를 조작할 수 있습니다.  
  
> [!TIP]
>  `XmlHttpRequest`에서 다양한 응답 형식을 사용하는 방법에 대한 자세한 내용은 [XMLHttpRequest.responseType](http://msdn.microsoft.com/en-us/8d7738d1-4bfd-4cf1-8015-174def089556), [XMLHttpRequest enhancements](http://msdn.microsoft.com/en-us/be09137c-6546-441b-b953-dcbf72b77069) 및 [다양한 콘텐츠 형식 다운로드(Windows 스토어 앱)](http://msdn.microsoft.com/en-us/c0006bbd-17f9-4c6a-af81-2acaf109111d)를 참조하세요.  
  
```JavaScript  
...  
<div id="xhrDiv"></div>  
...  
var name = "http://www.microsoft.com";  
var xhrDiv = document.getElementById("xhrDiv");  
  
var req = new XMLHttpRequest();  
req.open("GET", name, true);  
req.responseType = "arraybuffer";  
req.onreadystatechange = function () {  
if (req.readyState == req.DONE) {  
    var arrayResponse = req.response;  
    var dataView = new DataView(arrayResponse);  
    var ints = new Uint32Array(dataView.byteLength / 4);  
  
    xhrDiv.style.backgroundColor = "#00FF00";  
    xhrDiv.innerText = "Array is " + ints.length + "uints long";  
    }  
}  
req.send();  
```  
  
## <a name="arraybuffer"></a>ArrayBuffer  
 [ArrayBuffer 개체](../../javascript/reference/arraybuffer-object.md)는 다양한 형식화된 배열에 대한 데이터를 저장하는 데 사용되는 원시 데이터의 버퍼를 나타냅니다. `ArrayBuffer`에서 읽거나 여기에 쓸 수는 없지만 이 개체를 형식화된 배열 또는 [DataView 개체](../../javascript/reference/dataview-object.md)에 전달하여 원시 버퍼를 해석할 수 있습니다. `ArrayBuffer`를 사용하여 모든 데이터 종류 또는 혼합 형식 데이터를 저장할 수 있습니다.  
  
## <a name="dataview"></a>DataView  
 [DataView 개체](../../javascript/reference/dataview-object.md)를 사용하여 여러 종류의 이진 데이터를 읽고 `ArrayBuffer`의 임의 위치에 쓸 수 있습니다.  
  
## <a name="typed-arrays"></a>형식화된 배열  
 형식화된 배열 형식은 인덱싱 및 조작할 수 있는 [ArrayBuffer 개체](../../javascript/reference/arraybuffer-object.md)의 뷰를 나타냅니다. 모든 배열 형식의 길이는 고정 길이입니다.  
  
||||  
|-|-|-|  
|이름|크기(바이트)|설명|  
|[Int8Array 개체](../../javascript/reference/int8array-object.md)|1|8비트 2의 보수 부호 있는 정수|  
|[Uint8Array 개체](../../javascript/reference/uint8array-object.md)|1|8비트 부호 없는 정수|  
|[Int16Array 개체](../../javascript/reference/int16array-object.md)|2|16비트 2의 보수 부호 있는 정수|  
|[Uint16Array 개체](../../javascript/reference/uint16array-object.md)|2|16비트 부호 없는 정수|  
|[Int32Array 개체](../../javascript/reference/int32array-object.md)|4|32비트 2의 보수 부호 있는 정수|  
|[Uint32Array 개체](../../javascript/reference/uint32array-object.md)|4|32비트 부호 없는 정수|  
|[Float32Array 개체](../../javascript/reference/float32array-object.md)|4|32비트 IEEE 부동 소수점|  
|[Float64Array 개체](../../javascript/reference/float64array-object.md)|9|64비트 IEEE 부동 소수점|