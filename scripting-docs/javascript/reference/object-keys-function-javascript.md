---
title: "Object.keys 함수 (JavaScript) | Microsoft Docs"
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
- Object.keys method [JavaScript]
- keys method [JavaScript]
ms.assetid: cf4a7daf-cf28-4467-bc6b-f7f106ec3876
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0e725c3ab7206b04d9a900cb614b57c37dfc4351
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="objectkeys-function-javascript"></a>Object.keys 함수(JavaScript)
개체의 열거 가능한 속성 및 메서드 이름을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
Object.keys(object)  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|정의|  
|---------------|----------------|  
|`object`|필수 요소. 속성 및 메서드를 포함 하는 개체입니다. 이 만든 개체 또는 기존 문서 개체 모델 (DOM) 개체 수 있습니다.|  
  
## <a name="return-value"></a>반환 값  
 열거 가능한 속성의 이름 및 개체의 메서드를 포함 하는 배열입니다.  
  
## <a name="exceptions"></a>예외  
 에 대 한 제공 된 값은 `object` 인수는 개체의 이름이 아닙니다.는 `TypeError` 예외가 throw 됩니다.  
  
## <a name="remarks"></a>설명  
 `keys` 메서드 열거 가능한 속성 및 메서드의 이름만 반환 합니다. 열거 가능한 및 열거할 수 없는 속성 및 메서드를 둘 다의 이름을 반환할를 사용할 수 있습니다 [Object.getOwnPropertyNames 함수](../../javascript/reference/object-getownpropertynames-function-javascript.md)합니다.  
  
 에 대 한 내용은 `enumerable` 특성 속성 참조 [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md) 및 [Object.getOwnPropertyDescriptor 함수](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 세 가지 속성 및 메서드가 들어 있는 개체를 만듭니다. 다음 사용 하 여는 `keys` 메서드를 개체의 메서드와 속성을 가져옵니다.  
  
```JavaScript  
// Create a constructor function.  
function Pasta(grain, width, shape) {  
    this.grain = grain;  
    this.width = width;  
    this.shape = shape;  
  
    // Define a method.  
    this.toString = function () {  
        return (this.grain + ", " + this.width + ", " + this.shape);  
    }  
}  
  
// Create an object.  
var spaghetti = new Pasta("wheat", 0.2, "circle");  
  
// Put the enumerable properties and methods of the object in an array.  
var arr = Object.keys(spaghetti);  
document.write (arr);  
  
// Output:  
// grain,width,shape,toString  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 Pasta 개체에 "g" 문자로 시작 하는 모든 열거 가능한 속성의 이름을 표시 합니다.  
  
```JavaScript  
// Create a constructor function.  
function Pasta(grain, width, shape) {  
    this.grain = grain;  
    this.width = width;  
    this.shape = shape;  
}  
  
var polenta = new Pasta("corn", 1, "mush");  
  
var keys = Object.keys(polenta).filter(CheckKey);  
document.write(keys);  
  
// Check whether the first character of a string is "g".  
function CheckKey(value) {  
    var firstChar = value.substr(0, 1);  
    if (firstChar.toLowerCase() == "g")  
        return true;  
    else  
        return false;  
}  
  
// Output:  
// grain  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Object.getOwnPropertyNames 함수](../../javascript/reference/object-getownpropertynames-function-javascript.md)