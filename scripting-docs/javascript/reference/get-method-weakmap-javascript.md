---
title: "get 메서드 (WeakMap) (JavaScript) | Microsoft Docs"
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
ms.assetid: d922c55d-486d-4feb-aedc-1f4867c417d2
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 29decb7e6a050188b75639eb7cf4f27494b31da2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="get-method-weakmap-javascript"></a>get 메서드(WeakMap)(JavaScript)
지정 된 요소를 반환 하는 `WeakMap` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
weakmapObj.get(key)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `weakmapObj`  
 필수 요소. `WeakMap` 개체입니다.  
  
 `key`  
 필수 요소. 에 있는 요소의 키는 `WeakMap`합니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 키와 연결 된 개체를 반환 합니다. 경우는 `WeakMap` 에 없는 키를이 메서드는 반환 된 `undefined` 값입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 멤버를 검색 하는 방법을 보여 줍니다는 `WeakMap` 개체입니다.  
  
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