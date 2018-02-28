---
title: "Object.defineProperties 함수 (JavaScript) | Microsoft Docs"
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
- Object.defineProperties function [JavaScript]
ms.assetid: 2dae6658-a1c9-495f-bf06-bb3e964e6762
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 65f4f5817a105283a26c971bd98869d000ca0bc2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="objectdefineproperties-function-javascript"></a>Object.defineProperties 함수(JavaScript)
개체에 하나 이상의 속성을 추가하거나 기존 속성의 특성을 수정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object.defineProperties(object, descriptors)  
```  
  
## <a name="parameters"></a>매개 변수  
 `object`  
 필수 요소. 추가 하거나 속성을 수정 하는 개체입니다. 이 네이티브 수 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 또는 DOM 개체입니다.  
  
 `descriptors`  
 필수 요소. A [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 하나 이상의 설명자 개체를 포함 하는 개체입니다. 데이터 속성 또는 접근자 속성을 설명 하는 각 설명자 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 함수에 전달 된 개체입니다.  
  
## <a name="remarks"></a>설명  
 `descriptors` 인수는 하나 이상의 설명자 개체를 포함 하는 개체입니다.  
  
 A *data 속성* 를 저장 하 고 값을 검색 하는 속성입니다. 데이터 속성 설명자를 포함 한 `value` 특성은 `writable` 특성 또는 둘 다 합니다. 자세한 내용은 참조 [데이터 속성과 접근자 속성](../../javascript/advanced/data-properties-and-accessor-properties.md)합니다.  
  
 *접근자 속성* 속성 값을 설정 하거나 검색할 때마다 사용자가 제공한 함수를 호출 합니다. 접근자 속성 설명자를 포함 한 `set` 특성은 `get` 특성 또는 둘 다 합니다.  
  
 개체에 이미 지정 된 이름을 가진 속성이 속성 특성이 수정 됩니다. 자세한 내용은 참조 [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md)합니다.  
  
 개체를 만들고 새 개체에 속성을 추가 하려면 사용할 수 있습니다는 [Object.create 함수](../../javascript/reference/object-create-function-javascript.md)합니다.  
  
## <a name="adding-properties"></a>속성 추가  
 다음 예제에서는 `Object.defineProperties` 함수는 사용자 정의 개체를 데이터 속성과 접근자 속성을 추가 합니다.  
  
 이 예제에서는 개체 리터럴에 사용 하 여 만듭니다는 `descriptors` 개체는 `newDataProperty` 및 `newAccessorProperty` 설명자 개체입니다.  
  
```JavaScript  
var newLine = "<br />";  
  
var obj = {};  
Object.defineProperties(obj, {  
    newDataProperty: {  
        value: 101,  
        writable: true,  
        enumerable: true,  
        configurable: true  
    },  
    newAccessorProperty: {  
        set: function (x) {  
            document.write("in property set accessor" + newLine);  
            this.newaccpropvalue = x;  
        },  
        get: function () {  
            document.write("in property get accessor" + newLine);  
            return this.newaccpropvalue;  
        },  
        enumerable: true,  
        configurable: true  
    }});  
  
// Set the accessor property value.  
obj.newAccessorProperty = 10;  
document.write ("newAccessorProperty value: " + obj.newAccessorProperty + newLine);  
  
// Output:  
// in property set accessor  
// in property get accessor  
// newAccessorProperty value: 10  
  
```  
  
 이전 예제와 같이 다음 예에서는 리터럴 개체를 사용 하 여 동적으로 대신의 속성을 추가합니다.  
  
```JavaScript  
  
var newLine = "<br />";  
  
// Create the descriptors object.  
var descriptors = new Object();  
  
// Add a data property descriptor to the descriptors object.  
descriptors.newDataProperty = new Object();  
descriptors.newDataProperty.value = 101;  
descriptors.newDataProperty.writable = true;  
descriptors.newDataProperty.enumerable = true;  
descriptors.newDataProperty.configurable = true;  
  
// Add an accessor property descriptor to the descriptors object.  
descriptors.newAccessorProperty = new Object();  
descriptors.newAccessorProperty.set = function (x) {  
    document.write("in property set accessor" + newLine);  
    this.newaccpropvalue = x;  
};  
descriptors.newAccessorProperty.get = function () {  
    document.write("in property get accessor" + newLine);  
    return this.newaccpropvalue;  
};  
descriptors.newAccessorProperty.enumerable = true;  
descriptors.newAccessorProperty.configurable = true;  
  
// Call the Object.defineProperties function.  
var obj = new Object();  
Object.defineProperties(obj, descriptors);  
  
// Set the accessor property value.  
obj.newAccessorProperty = 10;  
document.write ("newAccessorProperty value: " + obj.newAccessorProperty + newLine);  
  
// Output:  
// in property set accessor  
// in property get accessor  
// newAccessorProperty value: 10  
  
```  
  
## <a name="modifying-properties"></a>속성 수정  
 개체에 대 한 속성 특성을 수정 하려면 다음 코드를 추가 합니다. `Object.defineProperties` 함수 수정는 `writable` 특성 `newDataProperty`, 수정 하 고는 `enumerable` 특성의 `newAccessorProperty`합니다. 추가 `anotherDataProperty` 개체에이 속성 이름이 이미 존재 하지 않기 때문에 있습니다.  
  
```  
Object.defineProperties(obj, {  
    newDataProperty: { writable: false },  
    newAccessorProperty: { enumerable: false },  
    anotherDataProperty: { value: "abc" }  
});  
```  
  
## <a name="requirements"></a>요구 사항  
 Internet Explorer 9 표준, Internet Explorer 10 표준 지원 및 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱. 다른 용도로 지원 되지 않습니다 DOM 개체에 대 한 Internet Explorer 8에서 지원 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Object.getOwnPropertyDescriptor 함수](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)   
 [Object.getOwnPropertyNames 함수](../../javascript/reference/object-getownpropertynames-function-javascript.md)   
 [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md)   
 [Object.create 함수](../../javascript/reference/object-create-function-javascript.md)   
 [Object 개체](../../javascript/reference/object-object-javascript.md)