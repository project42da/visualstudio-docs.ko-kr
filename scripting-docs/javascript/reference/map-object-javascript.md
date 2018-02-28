---
title: "Map 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Map
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: a91dbcbe-f58d-41a0-be15-8c9d30020327
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d89890f9fecaf61e47e136734ed7fefb7b73cabd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="map-object-javascript"></a>Map 개체(JavaScript)
키/값 쌍의 컬렉션입니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
mapObj = new Map()  
```  
  
## <a name="remarks"></a>설명  
 키 및 컬렉션의 값 형식일 수 있습니다. 기존 키를 사용하여 컬렉션에 값을 추가하는 경우 새 값이 이전 값을 대체합니다.  
  
## <a name="properties"></a>속성  
 다음 표에서는 `Map` 개체의 속성을 보여 줍니다.  
  
|속성|설명|  
|--------------|-----------------|  
|[생성자](../../javascript/reference/constructor-property-map.md)|맵을 만드는 함수를 지정 합니다.|  
|[프로토타입](../../javascript/reference/prototype-property-map.md)|지도 대 한 프로토타입의에 대 한 참조를 반환합니다.|  
|[size](../../javascript/reference/size-property-map-javascript.md)|Map에서 요소 수를 반환합니다.|  
  
## <a name="methods"></a>메서드  
 다음 표에서는 `Map` 개체의 메서드를 보여 줍니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[clear](../../javascript/reference/clear-method-map-javascript.md)|지도 요소를 모두 제거 합니다.|  
|[삭제](../../javascript/reference/delete-method-map-javascript.md)|지도에서 지정된 된 요소를 제거합니다.|  
|[forEach](../../javascript/reference/foreach-method-map-javascript.md)|각 지도 요소에 대 한 지정된 된 작업을 수행합니다.|  
|[get](../../javascript/reference/get-method-map-javascript.md)|맵에서 지정된 된 요소를 반환합니다.|  
|[가](../../javascript/reference/has-method-map-javascript.md)|반환 `true` 맵에 지정된 된 요소를 포함 하는 경우.|  
|[set](../../javascript/reference/set-method-map-javascript.md)|맵에 새 요소를 추가합니다.|  
|[toString](../../javascript/reference/tostring-method-map-javascript.md)|Map의 문자열 표현을 반환합니다.|  
|[valueOf](../../javascript/reference/valueof-method-map-javascript.md)|지정된 개체의 기본 값을 반환합니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Map`에 멤버를 추가한 다음 검색하는 방법을 보여 줍니다.  
  
```JavaScript  
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
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]