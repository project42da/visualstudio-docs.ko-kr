---
title: "컬렉션(JavaScript) | Microsoft Docs"
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
ms.assetid: 23c26185-6a7b-4b69-9d22-63e1841b4905
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# 컬렉션(JavaScript)
[Map](../../javascript/reference/map-object-javascript.md), [Set](../../javascript/reference/set-object-javascript.md) 및 [WeakMap](../../javascript/reference/weakmap-object-javascript.md)의 컬렉션 개체를 사용하여 값과 개체를 저장할 수 있습니다.  이러한 개체는 인덱스 대신 키 또는 값을 사용하여 멤버를 추가 및 검색하기 위한 편리한 메서드를 제공합니다.  인덱스를 사용하여 컬렉션의 멤버에 액세스하려면 `Array` 개체를 사용합니다.  자세한 내용은 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)을 참조하십시오.  
  
> [!CAUTION]
>  `Map`, `Set` 및 `WeakMap`은 Internet Explorer 11 이전 버전의 브라우저에서는 지원되지 않습니다.  버전 지원에 대한 자세한 내용은 [버전 정보](../../javascript/reference/javascript-version-information.md)을 참조하십시오.  
  
## 컬렉션 사용  
 `Map` 및 `WeakMap` 개체는 키\/값 쌍을 저장하고 해당 키를 사용하여 멤버를 추가, 검색 및 제거할 수 있습니다.  키와 값은 다양한 형식을 가질 수 있습니다.  `Set` 개체는 다양한 형식의 값을 저장합니다.  
  
 `Map` 및 `Set` 개체는 `forEach` 메서드를 사용하여 컬렉션 멤버를 열거할 수 있고 `size` 메서드를 사용하여 컬렉션의 크기를 확인할 수 있습니다.  이와 달리 `WeakMap` 개체는 열거할 수 없습니다.  이 컬렉션에 대해 키 참조는 약하게 유지됩니다.  응용 프로그램이 메모리에서 컬렉션의 각 멤버를 유지해야 하는지 여부를 가비지 수집기가 결정하도록 하려면 `WeakMap`을 사용합니다.  예를 들어, 캐시된 개체가 매우 크고 메모리에 개체를 불필요하게 유지하지 않는 시나리오를 캐싱하는 데 유용할 수 있습니다.  일부 시나리오에서 메모리 누수를 방지하기 위해 이 개체를 사용할 수 있습니다.  
  
 다음 예제에서는 `Map` 개체를 사용하는 방법을 보여 줍니다.  이 예제에서 `get` 및 `forEach`를 모두 사용하여 멤버에 액세스 합니다.  `forEach`의 콜백 함수는 현재 컬렉션 요소의 값, 현재 요소의 키 및 컬렉션 개체 자체를 제공하는 최대 세 개의 매개 변수를 사용할 수 있습니다.  
  
```javascript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
m.set({x:1}, 3);  
  
document.write(m.get(2));  
document.write("<br />");  
  
m.forEach(function (value, key, mapObj) {  
    document.write(item.toString() + "<br />");  
});  
  
// Output:  
// red  
  
// black  
// red  
// 2  
// 3  
  
```  
  
 `get`을 사용하여 멤버를 검색만 할 수 있다는 점을 제외하면 `WeakMap`의 사용은 `Map`과 비슷합니다.  예제는 [WeakMap](../../javascript/reference/weakmap-object-javascript.md) 개체를 참조하십시오.  
  
 다음 예제에서는 `Set` 개체를 사용하는 방법을 보여 줍니다.  이 예제에서 콜백 함수는 현재 컬렉션 요소의 값을 나타내는 매개 변수 하나만 사용합니다.  
  
```javascript  
var s = new Set();  
s.add("Thomas Jefferson");  
s.add(1776);  
s.add("founding father");  
  
s.forEach(function (value) {  
    document.write(item.toString() + ", ");  
});  
  
// Output:  
// Thomas Jefferson, 1776, founding father,  
  
```  
  
## 참고 항목  
 [고급 JavaScript](../../javascript/advanced/advanced-javascript.md)