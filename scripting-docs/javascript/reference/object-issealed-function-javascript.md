---
title: "Object.isSealed 함수 (JavaScript) | Microsoft Docs"
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
- properties [JavaScript], locking attributes
- isSealed function [JavaScript]
- Object.isSealed [JavaScript]
ms.assetid: af4f192e-cebe-44b9-8eef-90c096f5ae8f
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4d3b9cb603a456382e3b23e6f7d0037063027b98
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="objectissealed-function-javascript"></a>Object.isSealed 함수(JavaScript)
개체에서 기존 속성 특성을 수정할 수 없고 개체에 새 속성을 추가할 수 없으면 `true`를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
Object.isSealed(object)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `object`  
 필수 요소. 테스트할 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 `true`두 경우에서 다음 중:  
  
-   개체는 확장할 수 없게 나타냅니다 새 속성 개체에 추가할 수 없습니다.  
  
-   `configurable` 특성은 `false` 모든 기존 속성에 대 한 합니다.  
  
 함수가 반환 하는 경우 개체에 속성 `true` 개체가 확장할 수 없게 합니다.  
  
## <a name="exceptions"></a>예외  
 경우는 `object` 인수가 개체가 아닌 한 `TypeError` 예외가 throw 됩니다.  
  
## <a name="remarks"></a>설명  
 경우는 `configurable` 속성의 특성은 `false`, 속성 특성을 변경할 수 없습니다 및 속성을 삭제할 수 없습니다. 때 `writable` 은 `false`, 데이터 속성 값을 변경할 수 없습니다. 때 `configurable` 은 `false` 및 `writable` 은 `true`, `value` 및 `writable` 특성을 변경할 수 있습니다.  
  
 `Object.isSealed` 함수를 사용 하지 않습니다는 `writable` 반환 값을 확인 하는 속성의 특성입니다.  
  
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
|`Object.isSealed`|아니요|예|아니요|  
|[Object.isFrozen](../../javascript/reference/object-isfrozen-function-javascript.md)|아니요|예|예|  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Object.isSealed` 함수를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
// Create an object that has two properties.  
var obj = { pasta: "spaghetti", length: 10 };  
  
// Seal the object, and verify that it is sealed.  
Object.seal(obj);  
document.write(Object.isSealed(obj));  
document.write("<br/>");  
  
// Try to add a new property, and then verify that it is not added.   
obj.newProp = 50;  
document.write(obj.newProp);  
document.write("<br/>");  
  
// Try to delete a property, and then verify that it is still present.   
delete obj.length;  
document.write(obj.length);  
  
// Output:  
// true  
// undefined  
// 10  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Object.preventExtensions 함수](../../javascript/reference/object-preventextensions-function-javascript.md)   
 [Object.seal 함수](../../javascript/reference/object-seal-function-javascript.md)   
 [Object.freeze 함수](../../javascript/reference/object-freeze-function-javascript.md)   
 [Object.isExtensible 함수](../../javascript/reference/object-isextensible-function-javascript.md)   
 [Object.isFrozen 함수](../../javascript/reference/object-isfrozen-function-javascript.md)   
 [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md)   
 [Object.getOwnPropertyDescriptor 함수](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)