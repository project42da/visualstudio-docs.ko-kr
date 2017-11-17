---
title: "Object.getOwnPropertyNames 함수 (JavaScript) | Microsoft Docs"
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
- getOwnPropertyNames method [JavaScript]
- Object.getOwnPropertyNames method [JavaScript]
ms.assetid: 59f4b6b1-02be-44b3-a06c-a5ca8f70c3d8
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 76ca0036b9dedf7b4cee7b543469939e35dfe8d1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="objectgetownpropertynames-function-javascript"></a>Object.getOwnPropertyNames 함수(JavaScript)
개체의 고유 속성의 이름을 반환합니다. 개체의 고유한 속성은 해당 개체에 직접 정의 되 고 개체의 프로토타입에서 상속 되지 않습니다. 개체의 속성에는 필드 (개체) 및 함수를 모두 포함 됩니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
Object.getOwnPropertyNames(object)  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|정의|  
|---------------|----------------|  
|`object`|필수 요소. 고유의 속성을 포함 하는 개체입니다.|  
  
## <a name="return-value"></a>반환 값  
 개체의 고유 속성의 이름이 포함 된 배열입니다.  
  
## <a name="exceptions"></a>예외  
 에 대 한 제공 된 값은 `object` 인수는 개체의 이름이 아닙니다.는 `TypeError` 예외가 throw 됩니다.  
  
## <a name="remarks"></a>설명  
 `getOwnPropertyNames` 메서드 열거 가능한 및 열거할 수 없는 속성 및 메서드를 둘 다의 이름을 반환 합니다. 열거 가능한 속성 및 메서드의 이름만 반환 하려면 사용할 수 있습니다는 [Object.keys 함수](../../javascript/reference/object-keys-function-javascript.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 세 가지 속성 및 메서드가 들어 있는 개체를 만듭니다. 다음 사용 하 여는 `getOwnPropertyNames` 메서드를 가져올 개체의 고유 속성 (메서드 포함).  
  
```JavaScript  
function Pasta(grain, width, shape) {  
    // Define properties.  
    this.grain = grain;  
    this.width = width;  
    this.shape = shape;  
    this.toString = function () {  
        return (this.grain + ", " + this.width + ", " + this.shape);  
    }  
}  
  
// Create an object.  
var spaghetti = new Pasta("wheat", 0.2, "circle");  
  
// Get the own property names.  
var arr = Object.getOwnPropertyNames(spaghetti);  
document.write (arr);  
  
// Output:  
//   grain,width,shape,toString  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 자로 시작 하는 속성의 이름을 표시 '에 **복합** 개체로 구성 된 **Pasta** 생성자입니다.  
  
```JavaScript  
function Pasta(grain, size, shape) {  
    this.grain = grain;   
    this.size = size;   
    this.shape = shape;   
}  
  
var spaghetti = new Pasta("wheat", 2, "circle");  
  
var names = Object.getOwnPropertyNames(spaghetti).filter(CheckKey);  
document.write(names);   
  
// Check whether the first character of a string is 's'.   
function CheckKey(value) {  
    var firstChar = value.substr(0, 1);   
    if (firstChar.toLowerCase() == 's')  
        return true;   
    else  
         return false;   
}  
// Output:  
// size,shape  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Object.keys 함수](../../javascript/reference/object-keys-function-javascript.md)