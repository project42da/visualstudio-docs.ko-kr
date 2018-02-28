---
title: "Object.getOwnPropertyDescriptor 함수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- getOwnPropertyDescriptor method [JavaScript]
ms.assetid: 8f0e1c90-c4f9-44c4-bf76-726bacecbc14
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd147d567fc4d8a39d7a251d55772c40518e7a26
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="objectgetownpropertydescriptor-function-javascript"></a>Object.getOwnPropertyDescriptor 함수(JavaScript)
지정된 개체의 고유한 속성 설명자를 가져옵니다. 고유한 속성 설명자는 개체의 프로토타입에서 상속된 것이 아니라 개체에 직접 정의된 설명자입니다.  
  
## <a name="syntax"></a>구문  
  
```  
Object.getOwnPropertyDescriptor(object, propertyname)  
```  
  
## <a name="parameters"></a>매개 변수  
 `object`  
 필수 요소. 속성이 포함된 개체입니다.  
  
 `propertyname`  
 필수 요소. 속성의 이름입니다.  
  
## <a name="return-value"></a>반환 값  
 속성의 설명자입니다.  
  
## <a name="remarks"></a>설명  
 `Object.getOwnPropertyDescriptor` 함수를 사용하여 속성의 특성을 설명하는 설명자 개체를 가져올 수 있습니다.  
  
 [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md) 속성 추가 또는 수정 하는 데 사용 됩니다.  
  
## <a name="data-property-example"></a>데이터 속성 예제  
 다음 예제에서는 데이터 속성 설명자를 가져온 다음 이 설명자를 사용하여 속성을 읽기 전용으로 만듭니다.  
  
```JavaScript  
// Create a user-defined object.  
var obj = {};  
  
// Add a data property.  
obj.newDataProperty = "abc";  
  
// Get the property descriptor.  
var descriptor = Object.getOwnPropertyDescriptor(obj, "newDataProperty");  
  
// Change a property attribute.  
descriptor.writable = false;  
Object.defineProperty(obj, "newDataProperty", descriptor);  
  
```  
  
 속성 특성을 나열하려면 다음 코드를 이 예제에 추가할 수 있습니다.  
  
```JavaScript  
// Get the descriptor from the object.  
var desc2 = Object.getOwnPropertyDescriptor(obj, "newDataProperty");  
  
// List the descriptor attributes.  
for (var prop in desc2) {  
    document.write(prop + ': ' + desc2[prop]);  
    document.write("<br />");  
}  
  
// Output:  
// value: abc  
// writable: false  
// enumerable: true  
// configurable: true  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)]에서는 모든 기능이 지원됩니다.  
  
 [!INCLUDE[jsv58textspecific](../../javascript/reference/includes/jsv58textspecific-md.md)]에서는 DOM 개체를 지원하지만 사용자 정의 개체를 지원하지 않습니다. `enumerable` 및 `configurable` 특성을 지정할 수는 있지만 사용되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [문서 개체 모델 프로토타입, 2 부: 접근자 (getter/setter) 지원](http://msdn.microsoft.com/library/dd229916\(v=VS.85\).aspx)   
 [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md)