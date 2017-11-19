---
title: "Object.isFrozen 함수 (JavaScript) | Microsoft Docs"
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
helpviewer_keywords:
- isFrozen function [JavaScript]
- Object.isFrozen function [JavaScript]
ms.assetid: 6cf1bbc6-56e8-429b-8e2c-0024fa614acc
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3e1ccd11d5b4ef3b5f24dbfc8e815f0e3e156347
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="objectisfrozen-function-javascript"></a>Object.isFrozen 함수(JavaScript)
반환 `true` 개체에서 기존 속성 특성 및 값을 수정할 수 없는 경우 및 개체에 새 속성을 추가할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
Object.isFrozen(object)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `object`  
 필수 요소. 테스트할 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 `true`다음의 모든에 해당할 경우:  
  
-   개체는 확장할 수 없게 나타냅니다 새 속성 개체에 추가할 수 없습니다.  
  
-   `configurable` 특성은 `false` 모든 기존 속성에 대 한 합니다.  
  
-   `writable` 특성은 `false` 모든 기존 데이터 속성에 대 한 합니다.  
  
 함수 반환 된 개체에 기존 속성이 `true` 개체가 확장할 수 없게 합니다.  
  
## <a name="exceptions"></a>예외  
 경우는 `object` 인수가 개체가 아닌 한 `TypeError` 예외가 throw 됩니다.  
  
## <a name="remarks"></a>설명  
 경우는 `configurable` 속성의 특성은 `false`, 속성 특성을 변경할 수 없습니다 및 속성을 삭제할 수 없습니다. 때 `writable` 은 `false`, 데이터 속성 값을 변경할 수 없습니다. 때 `configurable` 은 `false` 및 `writable` 은 `true`, `value` 및 `writable` 특성을 변경할 수 있습니다.  
  
 속성 특성을 설정 하는 방법에 대 한 정보를 참조 하십시오. [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md)합니다. 속성의 특성을 가져오려면 사용할 수 있습니다는 [Object.getOwnPropertyDescriptor 함수](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)합니다.  
  
## <a name="related-functions"></a>관련된 함수  
 다음 관련된 함수는 개체 특성의 수정 되지 않도록 방지 합니다.  
  
|함수|개체 확장 가능-이루어집니다.|`configurable`로 설정 되어 `false` 각 속성에 대 한|`writable`로 설정 되어 `false` 각 속성에 대 한|  
|--------------|------------------------------------|--------------------------------------------------------|----------------------------------------------------|  
|[Object.preventExtensions](../../javascript/reference/object-preventextensions-function-javascript.md)|예|아니요|아니요|  
|[Object.seal](../../javascript/reference/object-seal-function-javascript.md)|예|예|아니요|  
|[Object.freeze](../../javascript/reference/object-freeze-function-javascript.md)|예|예|예|  
  
 다음 함수 반환 `true` 다음 표에 표시 된 조건에 모두 있습니다.  
  
|함수|개체는 확장 가능?|`configurable``false` 모든 속성에 대 한?|`writable``false` 모든 데이터 속성에 대 한?|  
|--------------|---------------------------|---------------------------------------------------|----------------------------------------------------|  
|[Object.isExtensible](../../javascript/reference/object-isextensible-function-javascript.md)|예|아니요|아니요|  
|[Object.isSealed](../../javascript/reference/object-issealed-function-javascript.md)|아니요|예|아니요|  
|`Object.isFrozen`|아니요|예|예|  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Object.isFrozen` 함수를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
// Create an object that has two properties.  
var obj = { pasta: "spaghetti", length: 10 };  
  
// Freeze the object, and verify that it is frozen.  
Object.freeze(obj);  
document.write(obj.isFrozen());  
  
// Try to add a new property, and then verify that it is not added.   
obj.newProp = 50;  
document.write (obj.newProp);  
document.write ("<br/>");  
  
// Try to delete a property, and then verify that it is still present.  
delete obj.length;  
document.write (obj.length);  
document.write ("<br/> ");  
  
// Try to change a property value, and then verify that it is not changed.  
obj.pasta = "linguini";  
document.write (obj.pasta);  
  
// Output:  
// true  
// undefined  
// 10  
// spaghetti  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Object.preventExtensions 함수](../../javascript/reference/object-preventextensions-function-javascript.md)   
 [Object.seal 함수](../../javascript/reference/object-seal-function-javascript.md)   
 [Object.freeze 함수](../../javascript/reference/object-freeze-function-javascript.md)   
 [Object.isExtensible 함수](../../javascript/reference/object-isextensible-function-javascript.md)   
 [Object.isSealed 함수](../../javascript/reference/object-issealed-function-javascript.md)   
 [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md)   
 [Object.getOwnPropertyDescriptor 함수](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)   
 [Object.getOwnPropertyNames 함수](../../javascript/reference/object-getownpropertynames-function-javascript.md)