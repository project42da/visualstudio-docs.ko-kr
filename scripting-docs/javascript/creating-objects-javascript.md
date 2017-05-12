---
title: "개체 만들기(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "생성자 함수"
  - "생성자, 속성 및 메서드 포함"
  - "개체 만들기"
  - "개체 만들기, 개체 만들기 정보"
  - "개체 만들기, 생성자 함수"
  - "개체 만들기, 프로토타입"
  - "사용자 지정 개체"
  - "사용자 지정 개체, 만들기"
  - "함수 생성자"
  - "개체 초기화, 생성자 사용"
  - "개체, 만들기[JavaScript]"
  - "프로토타입 개체"
ms.assetid: 58d1baa5-4fe8-4a56-a926-5b11765df704
caps.latest.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 19
---
# 개체 만들기(JavaScript)
JavaScript로 사용자 고유의 개체를 만들 수 있는 다양한 방법이 있습니다.  [Object 개체](../javascript/reference/object-object-javascript.md)를 직접 인스턴스화한 다음 사용자 고유의 속성 및 메서드를 추가할 수 있습니다.  또는 개체 리터럴 표기법을 사용하여 개체를 정의할 수 있습니다.  생성자 함수를 사용하여 개체를 정의할 수도 있습니다.  생성자 함수를 사용하는 방법에 대한 자세한 내용은 [생성자를 사용하여 형식 정의](../javascript/advanced/using-constructors-to-define-types.md)를 참조하세요.  
  
## 예제  
 다음 코드에서는 개체를 인스턴스화하고 일부 속성을 추가하는 방법을 보여 줍니다.  이 경우 `pasta` 개체에만 `grain`, `width` 및 `shape` 속성이 있습니다.  
  
```javascript  
var pasta = new Object();  
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
  
## 개체 리터럴  
 개체 인스턴스를 하나만 만들려는 경우 개체 리터럴 표기법을 사용할 수도 있습니다.  다음 코드에서는 개체 리터럴 표기법을 사용하여 개체를 인스턴스화하는 방법을 보여 줍니다.  
  
```javascript  
var pasta = {  
    grain: "wheat",  
    width: 0.5,  
    shape: "round"  
};  
```  
  
 생성자 내에서 개체 리터럴을 사용할 수도 있습니다.  
  
> [!CAUTION]
>  아래에 설명된 기능은 [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)]에서만 지원됩니다.  
  
 [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)]에서는 축약형 구문을 사용하여 개체 리터럴을 만들 수 있습니다.  
  
```javascript  
var key = 'a';  
var value = 5;  
  
// Older version  
var obj1 = {  
    key: key,  
    value: value  
};  
  
// Edge mode  
var obj2 = {key, value};  
  
console.log(obj2);  
  
// Output:  
// [object Object] {key: "a", value: 5}  
```  
  
 다음 예제에서는 축약형 구문을 사용하여 개체 리터럴에서 메서드를 정의하는 방법을 보여 줍니다.  
  
```javascript  
// Older versions  
var obj = {  
    method1: function() {},  
    method2: function() {}  
};  
  
// Edge mode  
var obj = {  
    method1() {},  
    method2() {}  
};  
```  
  
 [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)]에서는 개체 리터럴에서 속성 이름을 동적으로 설정할 수도 있습니다.  다음 코드 예제에서는 set 구문을 사용하여 동적으로 개체의 속성 이름을 만듭니다.  
  
```javascript  
var propName = "prop_42";  
  
var obj = {  
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
  
```javascript  
var propName = "prop_42";  
  
var obj = {  
    get [propName]() {  
        return 777;  
    }  
}  
  
console.log(obj.prop_42);  
  
// Output:  
// 777  
```  
  
 다음 코드 예제에서는  [화살표 함수 구문](../javascript/functions-javascript.md)을 사용하여 속성 이름에 42를 추가하는 계산된 속성을 만듭니다.  
  
```javascript  
var obj = {  
    [ 'prop_' + (() => 42)() ]: 42  
};  
```