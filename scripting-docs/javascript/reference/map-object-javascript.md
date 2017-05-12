---
title: "Map 개체(JavaScript) | Microsoft Docs"
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
  - "Map"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: a91dbcbe-f58d-41a0-be15-8c9d30020327
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# Map 개체(JavaScript)
키\/값 쌍의 컬렉션입니다.  
  
## 구문  
  
```javascript  
mapObj = new Map()  
```  
  
## 설명  
 컬렉션의 키 및 값은 모든 형식이 허용됩니다.  기존 키를 사용하여 컬렉션에 값을 추가하는 경우 새 값이 이전 값을 대체합니다.  
  
## 속성  
 다음 표에서는 `Map` 개체의 속성을 보여 줍니다.  
  
|속성|설명|  
|--------|--------|  
|[생성자](../../javascript/reference/constructor-property-map.md)|맵을 만드는 함수를 지정합니다.|  
|[프로토타입\(Prototype\)](../../javascript/reference/prototype-property-map.md)|맵의 프로토타입에 대한 참조를 반환합니다.|  
|[size](../../javascript/reference/size-property-map-javascript.md)|맵의 요소 수를 반환합니다.|  
  
## 메서드  
 다음 표에서는 `Map` 개체의 메서드를 보여 줍니다.  
  
|방법|설명|  
|--------|--------|  
|[clear](../../javascript/reference/clear-method-map-javascript.md)|맵에서 요소를 모두 제거합니다.|  
|[삭제](../../javascript/reference/delete-method-map-javascript.md)|맵에서 지정된 요소를 제거합니다.|  
|[forEach](../../javascript/reference/foreach-method-map-javascript.md)|맵의 각 요소에 대해 지정된 작업을 수행합니다.|  
|[get](../../javascript/reference/get-method-map-javascript.md)|맵에서 지정된 요소를 반환합니다.|  
|[has](../../javascript/reference/has-method-map-javascript.md)|맵이 지정된 요소를 포함하는 경우 `true`를 반환합니다.|  
|[set](../../javascript/reference/set-method-map-javascript.md)|맵에 새 요소를 추가합니다.|  
|[toString](../../javascript/reference/tostring-method-map-javascript.md)|맵의 문자열 표현을 반환합니다.|  
|[valueOf](../../javascript/reference/valueof-method-map-javascript.md)|지정한 개체의 원시 값을 반환합니다.|  
  
## 예제  
 다음 예제에서는 `Map`에 멤버를 추가한 다음 검색하는 방법을 보여 줍니다.  
  
```javascript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
m.set({x:1}, 3);  
  
m.forEach(function (item, key, mapObj) {  
    document.write(item.toString() + "<br />");  
});  
  
document.write("<br />");  
document.write(m.get(2));  
  
// Output:  
// black  
// red  
// 2  
// 3  
//  
// red  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]