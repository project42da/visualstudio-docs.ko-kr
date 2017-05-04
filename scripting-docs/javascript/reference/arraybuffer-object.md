---
title: "ArrayBuffer 개체 | Microsoft Docs"
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
ms.assetid: 9fda1261-f450-493b-b3db-ecfa9ca93cd7
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# ArrayBuffer 개체
다른 형식화된 배열용으로 데이터를 저장하는 데 사용되는 이진 데이터의 원시 버퍼를 나타냅니다.  `ArrayBuffers`는 직접 읽거나 쓸 수 없지만 형식화된 배열이나 [DataView 개체](../../javascript/reference/dataview-object.md)로 전달하여 필요에 따라 원시 버퍼를 해석할 수는 있습니다.  
  
 형식화된 배열에 대한 자세한 내용은 [형식화된 배열](../../javascript/advanced/typed-arrays-javascript.md)을 참조하세요.  
  
## 구문  
  
```javascript  
  
arrayBuffer = new ArrayBuffer(length);  
```  
  
## 매개 변수  
 `arrayBuffer`  
 필수 요소.  `ArrayBuffer` 개체가 할당되는 변수 이름입니다.  
  
 `length`  
 버퍼의 길이입니다.  Arraybuffer의 콘텐츠는 0으로 초기화됩니다.  요청된 바이트 수를 할당할 수 없으면 예외가 발생합니다.  
  
## 속성  
 다음 표에서는 `ArrayBuffer` 개체의 속성을 보여 줍니다.  
  
|속성|설명|  
|--------|--------|  
|[byteLength 속성](../../javascript/reference/bytelength-property-arraybuffer.md)|읽기 전용입니다.  ArrayBuffer의 길이\(바이트\)입니다.|  
  
## 함수  
 다음 표에서는 `ArrayBuffer` 개체의 함수를 보여줍니다.  
  
|속성|설명|  
|--------|--------|  
|[ArrayBuffer.isView 함수](../../javascript/reference/arraybuffer-isview-function-arraybuffer.md)|개체에서 버퍼 뷰를 제공하는지 여부를 결정합니다.|  
  
## 메서드  
 다음 표에서는 `ArrayBuffer` 개체의 메서드를 보여 줍니다.  
  
|속성|설명|  
|--------|--------|  
|[slice 메서드](../../javascript/reference/slice-method-arraybuffer.md)|`ArrayBuffer`의 한 섹션을 반환합니다.|  
  
## 예제  
 다음 예에서는 ArrayBuffer 개체를 사용하여 [XMLHttpRequest](http://msdn.microsoft.com/library/ie/ms535874\(v=vs.85\).aspx)에서 가져온 이진 데이터를 처리하는 방법을 보여 줍니다.  [DataView 개체](../../javascript/reference/dataview-object.md)를 사용하여 개별 값을 가져올 수 있습니다.  
  
```javascript  
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
  
## 설명  
 `XmlHttpRequest` 사용에 대한 자세한 내용은 [XMLHttpRequest enhancements](http://msdn.microsoft.com/ko-kr/be09137c-6546-441b-b953-dcbf72b77069)를 참조하십시오.  
  
## 요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]