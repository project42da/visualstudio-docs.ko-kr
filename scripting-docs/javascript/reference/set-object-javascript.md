---
title: "Set 개체(JavaScript) | Microsoft Docs"
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
  - "Set"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 4a4dd749-2a76-44fb-9cb0-a3ef317f75fb
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# Set 개체(JavaScript)
임의의 형식의 고유한 값의 컬렉션입니다.  
  
## 구문  
  
```  
setObj = new Set()  
  
```  
  
## 설명  
 고유하지 않은 값을 `Set`에 추가하려고 하면 새 값이 컬렉션에 추가되지 않습니다.  
  
## 속성  
 다음 표에서는 `Set` 개체의 속성을 보여 줍니다.  
  
|속성|설명|  
|--------|--------|  
|[생성자](../../javascript/reference/constructor-property-set.md)|집합을 만드는 함수를 지정합니다.|  
|[프로토타입\(Prototype\)](../../javascript/reference/prototype-property-set.md)|집합의 프로토타입에 대한 참조를 반환합니다.|  
|[size](../../javascript/reference/size-property-set-javascript.md)|집합에 있는 요소 수를 반환합니다.|  
  
## 메서드  
 다음 표에서는 `Set` 개체의 메서드를 보여 줍니다.  
  
|방법|설명|  
|--------|--------|  
|[추가](../../javascript/reference/add-method-set-javascript.md)|집합에 요소를 추가합니다.|  
|[clear](../../javascript/reference/clear-method-set-javascript.md)|집합에서 요소를 모두 제거합니다.|  
|[삭제](../../javascript/reference/delete-method-set-javascript.md)|집합에서 지정된 요소를 제거합니다.|  
|[forEach](../../javascript/reference/foreach-method-set-javascript.md)|집합의 각 요소에 대해 지정된 작업을 수행합니다.|  
|[has](../../javascript/reference/has-method-set-javascript.md)|집합이 지정된 요소를 포함하는 경우 `true`를 반환합니다.|  
|[toString](../../javascript/reference/tostring-method-set-javascript.md)|집합의 문자열 표현을 반환합니다.|  
|[valueOf](../../javascript/reference/valueof-method-set-javascript.md)|지정한 개체의 원시 값을 반환합니다.|  
  
## 예제  
 다음 예제에서는 집합에 멤버를 추가한 다음 검색하는 방법을 보여 줍니다.  
  
```javascript  
var s = new Set();  
s.add("Thomas Jefferson");  
s.add(1776);  
s.add("founding father");  
  
s.forEach(function (item) {  
    document.write(item.toString() + ", ");  
});  
  
// Output:  
// Thomas Jefferson, 1776, founding father,  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]