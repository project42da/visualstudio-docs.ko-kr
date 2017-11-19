---
title: "ArrayBuffer.isView 함수 (ArrayBuffer) | Microsoft Docs"
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
ms.assetid: 1887324f-892b-4fcd-ad33-748ba9517a06
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5aaae2acb38aa2f8c4b5e49ea203e86665315700
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="arraybufferisview-function-arraybuffer"></a>ArrayBuffer.isView 함수(ArrayBuffer)
개체에서 버퍼 뷰를 제공하는지 여부를 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
ArrayBuffer.isView(object)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `object`  
 필수 요소. 테스트할 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 다음 중 하나가 참인 경우 `true`입니다.  
  
-   `object`가 `DataView` 개체입니다.  
  
-   `object`가 형식화된 배열입니다.  
  
 그렇지 않은 경우 메서드는 `false`를 반환합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예제  
 다음 예에서는 `isView` 함수를 사용하여 형식화된 배열과 `DataView` 개체를 테스트하는 방법을 보여 줍니다.  
  
```JavaScript  
var uint = new UInt8ClampedArray(10);  
  
if(console && console.log) {  
    console.log( ArrayBuffer.isView(uint) ); // Outputs true  
{  
var dataView = new DataView(uint.buffer);  
  
if(console && console.log) {  
    console.log( ArrayBuffer.isView(dataView) ); // Outputs true.  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Uint8ClampedArray 개체](../../javascript/reference/uint8clampedarray-object-javascript.md)