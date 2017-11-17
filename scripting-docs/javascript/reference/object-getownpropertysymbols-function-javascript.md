---
title: "Object.getOwnPropertySymbols 함수 (JavaScript) | Microsoft Docs"
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
ms.assetid: 68dd69b9-5a33-44c2-ba5f-21a4ae6c0879
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2bcddba77305e30e4c5ae13f6b1fc5c9385b7108
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="objectgetownpropertysymbols-function-javascript"></a>Object.getOwnPropertySymbols 함수(JavaScript)
개체의 고유한 기호 속성을 반환합니다. 개체의 고유한 기호 속성은 개체의 프로토타입에서 상속되지 않고 해당 개체에서 직접 정의된 속성입니다.  
  
## <a name="syntax"></a>구문  
  
```  
Object.getOwnPropertySymbols(object);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `object`  
 필수 요소. 고유한 기호를 포함하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 개체의 고유한 기호를 포함하는 배열입니다.  
  
## <a name="remarks"></a>설명  
 `Object.getOwnPropertySymbols`를 사용하여 개체의 기호 속성을 가져와야 합니다. `Object.getOwnPropertyNames`는 기호 속성을 반환하지 않습니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 개체의 기호 속성을 가져오는 방법을 보여 줍니다.  
  
```JavaScript  
var obj = {};  
var key = Symbol('description');  
  
obj[key] = 'data';  
  
var symbols = Object.getOwnPropertySymbols(obj);  
  
console.log(s[0].toString());  
  
// Output:  
// undefined  
// Symbol(description)  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]