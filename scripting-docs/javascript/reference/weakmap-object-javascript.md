---
title: "WeakMap 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: WeakMap
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 4682d2dc-caf9-4fa8-8313-a0a0b804fd1d
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8de97f8acb94921090696e9019a1df5d945db7c6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="weakmap-object-javascript"></a>WeakMap 개체(JavaScript)
각 키가 개체 참조인 키/값 쌍 컬렉션입니다.  
  
## <a name="syntax"></a>구문  
  
```  
weakmapObj = new WeakMap()  
```  
  
## <a name="remarks"></a>설명  
 A `WeakMap` 개체를 열거할 수 없습니다.  
  
 기존 키를 사용하여 컬렉션에 값을 추가하는 경우 새 값이 이전 값을 대체합니다.  
  
 에 `WeakMap` 개체, 주요 개체에 대 한 참조는 '약하게' 유지 됩니다. 즉 `WeakMap` 키 개체에서 가비지 수집 해도 됩니다. 참조가 없는 경우 (이외의 `WeakMap`) 키 개체를 가비지 수집기 키 개체를 수집할 수 있습니다.  
  
## <a name="properties"></a>속성  
 다음 표에서는 `WeakMap` 개체의 속성을 보여 줍니다.  
  
|속성|설명|  
|--------------|-----------------|  
|[생성자](../../javascript/reference/constructor-property-weakmap.md)|`WeakMap`을 만드는 함수를 지정합니다.|  
|[프로토타입](../../javascript/reference/prototype-property-weakmap.md)|`WeakMap`에 대한 프로토타입의 참조를 반환합니다.|  
  
## <a name="methods"></a>메서드  
 다음 표에서는 `WeakMap` 개체의 메서드를 보여 줍니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[clear](../../javascript/reference/clear-method-weakmap-javascript.md)|
          `WeakMap`에서 요소를 모두 제거합니다.|  
|[삭제](../../javascript/reference/delete-method-weakmap-javascript.md)|지정 된 요소를 제거는 `WeakMap`합니다.|  
|[get](../../javascript/reference/get-method-weakmap-javascript.md)|지정 된 요소를 반환 하는 `WeakMap`합니다.|  
|[가](../../javascript/reference/has-method-weakmap-javascript.md)|반환 `true` 경우는 `WeakMap` 지정된 된 요소를 포함 합니다.|  
|[set](../../javascript/reference/set-method-weakmap-javascript.md)|`WeakMap`에 새 요소를 추가합니다.|  
|[toString](../../javascript/reference/tostring-method-weakmap-javascript.md)|문자열 표현을 반환는 `WeakMap`합니다.|  
|[valueOf](../../javascript/reference/valueof-method-weakmap-javascript.md)|지정된 개체의 기본 값을 반환합니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 멤버를 추가 하는 방법을 보여 줍니다는 `WeakMap` 다음 검색 하 고 개체입니다.  
  
```JavaScript  
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
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]