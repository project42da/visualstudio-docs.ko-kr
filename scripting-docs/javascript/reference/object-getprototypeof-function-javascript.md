---
title: "Object.getPrototypeOf 함수 (JavaScript) | Microsoft Docs"
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
- getPrototypeOf function [JavaScript]
- Object.getPrototypeOf function [JavaScript]
ms.assetid: 1c59cd7a-a7e2-4c5c-83ec-e6bd2b104d9f
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0c752c57fcc47192bb43790b2e93dd74fcdfbb65
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="objectgetprototypeof-function-javascript"></a>Object.getPrototypeOf 함수(JavaScript)
개체의 프로토타입을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
Object.getPrototypeOf(object)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `object`  
 필수 요소. 프로토타입의 참조 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 프로토타입에 `object` 인수입니다. 프로토타입 개체 이기도합니다.  
  
## <a name="exceptions"></a>예외  
 경우는 `object` 인수가 개체가 아닌 한 `TypeError` 예외가 throw 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Object.getPrototypeOf` 함수를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
// Create a constructor function.  
function Pasta(grain, width) {  
    this.grain = grain;  
    this.width = width;  
}  
// Create an object from the pasta constructor.  
var spaghetti = new Pasta("wheat", 0.2);  
  
// Obtain the prototype from the object.  
var proto = Object.getPrototypeOf(spaghetti);  
  
// Add a property to the prototype and validate that  
// the original object has the property.  
proto.foodgroup = "carbohydrates";  
document.write(spaghetti.foodgroup + " ");  
  
// Verify that the prototype obtained from the object  
// is the same as the prototype of the constructor.  
var result = (proto === Pasta.prototype);  
document.write(result + " ");  
  
// Verify that prototype obtained from the object  
// is a prototype of the original object.  
var result = proto.isPrototypeOf(spaghetti);  
document.write(result);  
  
// Output: carbohydrates true true  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Object.getPrototypeOf` 데이터 형식의 유효성을 검사 하는 함수입니다.  
  
```JavaScript  
var reg = /a/;  
var result = (Object.getPrototypeOf(reg) === RegExp.prototype);  
document.write(result + " ");  
  
var err = new Error("an error");  
var result = (Object.getPrototypeOf(err) === Error.prototype);  
document.write(result);  
  
// Output: true true  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [prototype 속성 (Object)](../../javascript/reference/prototype-property-object-javascript.md)   
 [isPrototypeOf 메서드(Object)](../../javascript/reference/isprototypeof-method-object-javascript.md)