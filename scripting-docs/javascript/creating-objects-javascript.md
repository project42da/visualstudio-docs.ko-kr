---
title: "개체 만들기(JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- constructors, including properties and methods
- function constructor
- creating objects, constructor functions
- constructor functions
- prototype objects
- creating objects
- custom objects, creating
- creating objects, about creating objects
- objects, creating [JavaScript]
- creating objects, prototypes
- custom objects
- initializing objects, using constructors
ms.assetid: 58d1baa5-4fe8-4a56-a926-5b11765df704
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0ba7962179cc2f0fcb972caee692edabee368c7d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="creating-objects-javascript"></a>개체 만들기(JavaScript)
JavaScript로 사용자 고유의 개체를 만들 수 있는 다양한 방법이 있습니다. [Object 개체](../javascript/reference/object-object-javascript.md)를 직접 인스턴스화한 다음, 사용자 고유의 속성 및 메서드를 추가할 수 있습니다. 또는 개체 리터럴 표기법을 사용하여 개체를 정의할 수 있습니다. 생성자 함수를 사용하여 개체를 정의할 수도 있습니다. 생성자 함수를 사용하는 방법에 대한 자세한 내용은 [생성자를 사용하여 형식 정의](../javascript/advanced/using-constructors-to-define-types.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 코드에서는 개체를 인스턴스화하고 일부 속성을 추가하는 방법을 보여 줍니다. 이 경우 `pasta` 개체에만 `grain`, `width` 및 `shape` 속성이 있습니다.  
  
```JavaScript  
const pasta = new Object();  
pasta.grain = "wheat";  
pasta.width = 0.5;  
pasta.shape = "round";  
pasta.getShape = function() {   
    return this.shape;   
};  
document.write(pasta.grain);  
document.write("<br/>");  
document.write(pasta.getShape());  
  
// Output:  
// wheat  
// round  
  
```  
  
## <a name="object-literals"></a>개체 리터럴  
 개체 인스턴스를 하나만 만들려는 경우 개체 리터럴 표기법을 사용할 수도 있습니다. 다음 코드에서는 개체 리터럴 표기법을 사용하여 개체를 인스턴스화하는 방법을 보여 줍니다.  
  
```JavaScript  
const pasta = {  
    grain: "wheat",  
    width: 0.5,  
    shape: "round"  
};  
```  
  
 생성자 내에서 개체 리터럴을 사용할 수도 있습니다.  
  
> [!CAUTION]
>  아래에 설명된 기능은 [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)]에서만 지원됩니다.  
  
 [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)]에서는 축약형 구문을 사용하여 개체 리터럴을 만들 수 있습니다.  
  
```JavaScript  
const key = 'a';  
const value = 5;  
  
// Older version  
const obj1 = {  
    key: key,  
    value: value  
};  
  
// Edge mode  
const obj2 = {key, value};  
  
console.log(obj2);  
  
// Output:  
// [object Object] {key: "a", value: 5}  
```  
  
 다음 예제에서는 축약형 구문을 사용하여 개체 리터럴에서 메서드를 정의하는 방법을 보여 줍니다.  
  
```JavaScript  
// Older versions  
const obj = {  
    method1: function() {},  
    method2: function() {}  
};  
  
// Edge mode  
const obj = {  
    method1() {},  
    method2() {}  
};  
```  
  
 [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)]에서는 개체 리터럴에서 속성 이름을 동적으로 설정할 수도 있습니다. 다음 코드 예제에서는 set 구문을 사용하여 동적으로 개체의 속성 이름을 만듭니다.  
  
```JavaScript  
const propName = "prop_42";  
  
const obj = {  
    value: 0,  
    set [propName](v) {  
        this.value = v;  
    }  
}  
  
console.log(obj.value);  
// Runs the setter property.  
obj.prop_42 = 777;  
console.log(obj.value);  
  
// Output:  
// 0  
// 777  
  
```  
  
 다음 코드 예제에서는 get 구문을 사용하여 동적으로 개체의 속성 이름을 만듭니다.  
  
```JavaScript  
const propName = "prop_42";  
  
const obj = {  
    get [propName]() {  
        return 777;  
    }  
}  
  
console.log(obj.prop_42);  
  
// Output:  
// 777  
```  
  
 다음 코드 예제에서는 [화살표 함수 구문](../javascript/functions-javascript.md)을 사용하여 속성 이름에 42를 추가하는 계산된 속성을 만듭니다.  
  
```JavaScript  
const obj = {  
    [ 'prop_' + (() => 42)() ]: 42  
};  
```
