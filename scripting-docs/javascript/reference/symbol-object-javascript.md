---
title: "Symbol 개체(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 2ad059f1-4b7f-4758-882a-c74ce1283ab0
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# Symbol 개체(JavaScript)
고유 식별자를 만들 수 있습니다.  
  
## 구문  
  
```  
obj = Symbol(desc)  
```  
  
#### 매개 변수  
 `desc`  
 선택 사항입니다.  기호에 대한 설명입니다.  
  
## 설명  
 Symbol 개체를 사용하면 기존 개체 속성을 방해할 가능성, 의도하지 않은 표시 유형 및 다른 코드에 의한 조정되지 않은 추가 없이 속성을 기존 개체에 추가할 수 있습니다.  
  
 Symbol은 기본 데이터 형식입니다.  Symbol 개체는 `new` 연산자를 사용하여 만들 수 없습니다.  
  
 Symbol 개체를 전체 기호 레지스트리에 추가하려면 `Symbol.for` 및 `Symbol.keyFor` 함수를 사용합니다.  기호를 문자열로 직렬화하는 경우 전역 기호 레지스트리를 사용하여 특정 문자열 맵이 모든 조회에 대해 올바른 기호를 보여주도록 합니다.  
  
 JavaScript에는 전역 범위에서 사용할 수 있는 다음과 같은 기본 제공 기호 값이 포함됩니다.  
  
|기호|설명|  
|--------|--------|  
|`Symbol.hasInstance`|이 메서드는 생성자 개체가 개체를 생성자의 인스턴스 중 하나로 인식하는지 여부를 결정합니다.  `instanceof` 연산자에 의해 내부적으로 사용됩니다.|  
|`Symbol.isConcatSpreadable`|이 속성은 개체가 `Array.concat`에 의해 배열 요소로 평면화되어야 하는지 여부를 나타내는 부울 값을 반환합니다.|  
|`Symbol.iterator`|이 메서드는 개체에 대한 기본 반복기를 반환합니다.  `for…of` 문에 의해 내부적으로 사용됩니다.|  
|`Symbol.toPrimitive`|이 메서드는 해당 기본값으로 개체를 변환합니다.  `ToPrimitive` 추상 작업에 의해 내부적으로 사용됩니다.|  
|`Symbol.toStringTag`|이 속성은 개체의 기본 문자열 설명을 만들기 위해 사용되는 문자열 값을 반환합니다.  기본 제공 메서드 `Object.toString` 메서드에 의해 내부적으로 사용됩니다.|  
|`Symbol.unscopables`|이 속성은 연결된 개체의 `with` 환경 바인딩에서 제외된 속성이 있는 개체를 반환합니다.|  
  
## Functions  
 다음 표에서는 `Symbol` 개체의 함수를 보여줍니다.  
  
|||  
|-|-|  
|속성|설명|  
|[Symbol.for](../../javascript/reference/symbol-for-function-javascript.md)|지정된 키에 대한 기호를 반환하거나 키가 없는 경우 새 키를 사용하여 새 기호 개체를 만듭니다.|  
|[Symbol.keyFor](../../javascript/reference/symbol-keyfor-function-javascript.md)|지정된 기호에 대한 키를 반환합니다.|  
|||  
  
## 예제  
  
```javascript  
(function() {  
  
    // module-scoped symbol  
    var key = Symbol("description");  
  
    function MyClass(privateData) {  
      this[key] = privateData;  
    }  
  
    MyClass.prototype = {  
      someFunc: function() {  
        return "data: " + this[key];  
      }  
    };  
  
    var c = new MyClass("private data")  
    console.log(key);  
    console.log(c["key"]);  
    console.log(c.someFunc());  
  
})();  
  
// Output:  
// undefined  
// undefined  
// data: private data  
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]