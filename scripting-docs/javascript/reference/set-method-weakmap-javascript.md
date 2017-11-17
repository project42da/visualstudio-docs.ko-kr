---
title: "set 메서드 (WeakMap) (JavaScript) | Microsoft Docs"
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
ms.assetid: 29fc72b1-224f-4f19-8c06-5d926d695b03
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c916bda13c7bd973b37c4e4cb6b81e327ee5de54
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="set-method-weakmap-javascript"></a>set 메서드(WeakMap)(JavaScript)
`WeakMap` 개체에 새 요소를 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
weakmapObj.set(key, value)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `weakmapObj`  
 필수 요소. `WeakMap` 개체입니다.  
  
 `key`  
 필수 요소. 추가할 요소의 키를 나타내는 개체입니다. 이것은 개체 참조여야 합니다.  
  
 `value`  
 필수 요소. 추가할 요소의 값입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 새로운 키/값 쌍을 포함하는 `WeakMap` 개체를 반환합니다.  
  
## <a name="remarks"></a>설명  
 기존 키를 사용하여 컬렉션에 값을 추가하는 경우 새 값이 이전 값을 대체합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `WeakMap` 개체에 멤버를 추가하는 방법을 보여 줍니다.  
  
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
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]