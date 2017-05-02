---
title: "WeakMap 개체(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "WeakMap"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 4682d2dc-caf9-4fa8-8313-a0a0b804fd1d
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# WeakMap 개체(JavaScript)
각 키의 키\/값 쌍의 컬렉션은 개체 참조입니다.  
  
## 구문  
  
```  
weakmapObj = new WeakMap()  
```  
  
## 설명  
 `WeakMap` 개체는 열거할 수 없습니다.  
  
 기존 키를 사용하여 컬렉션에 값을 추가하는 경우 새 값이 이전 값을 대체합니다.  
  
 `WeakMap` 개체에서 키 개체에 대한 참조는 '약하게' 유지됩니다.  `WeakMap`이 주요 개체에서 발생하는 가비지 컬렉션을 방지하지 않음을 의미합니다.  키 개체에 대한 참조가 없으면\(`WeakMap` 제외\) 가비지 수집기는 키 개체를 수집할 수도 있습니다.  
  
## 속성  
 다음 표에서는 `WeakMap` 개체의 속성을 보여 줍니다.  
  
|속성|설명|  
|--------|--------|  
|[생성자](../../javascript/reference/constructor-property-weakmap.md)|`WeakMap`을 만드는 함수를 지정합니다.|  
|[프로토타입\(Prototype\)](../../javascript/reference/prototype-property-weakmap.md)|`WeakMap`의 프로토타입에 대한 참조를 반환합니다.|  
  
## 메서드  
 다음 표에서는 `WeakMap` 개체의 메서드를 보여 줍니다.  
  
|방법|설명|  
|--------|--------|  
|[clear](../../javascript/reference/clear-method-weakmap-javascript.md)|`WeakMap`에서 요소를 모두 제거합니다.|  
|[삭제](../../javascript/reference/delete-method-weakmap-javascript.md)|`WeakMap`에서 지정된 요소를 제거합니다.|  
|[get](../../javascript/reference/get-method-weakmap-javascript.md)|`WeakMap`에서 지정된 요소를 반환합니다.|  
|[has](../../javascript/reference/has-method-weakmap-javascript.md)|`WeakMap`이 지정된 요소를 포함하는 경우 `true`를 반환합니다.|  
|[set](../../javascript/reference/set-method-weakmap-javascript.md)|`WeakMap`에 새 요소를 추가합니다.|  
|[toString](../../javascript/reference/tostring-method-weakmap-javascript.md)|`WeakMap`의 문자열 표현을 반환합니다.|  
|[valueOf](../../javascript/reference/valueof-method-weakmap-javascript.md)|지정한 개체의 원시 값을 반환합니다.|  
  
## 예제  
 다음 예제에서는 `WeakMap` 개체에 멤버를 추가한 다음 검색하는 방법을 보여 줍니다.  
  
```javascript  
var dog = {  
    breed: "yorkie"  
}  
  
var cat = {  
    breed: "burmese"  
}  
  
var wm = new WeakMap();  
wm.set(dog, "fido");  
wm.set(cat, "pepper");  
  
document.write(wm.get(dog) + ": ");  
document.write(dog.breed);  
document.write("<br />");  
document.write(wm.get(cat) + ": ");  
document.write(cat.breed);  
  
// Output:  
// fido: yorkie  
// pepper: burmese  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]