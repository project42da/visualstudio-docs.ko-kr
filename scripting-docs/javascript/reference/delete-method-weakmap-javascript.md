---
title: "delete 메서드 (WeakMap) (JavaScript) | Microsoft Docs"
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
ms.assetid: 7d54ae55-e514-45ba-b403-d1eee46837d2
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fd4cec06b77b7198e23d7e455849b5c0bf6d7ff9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="delete-method-weakmap-javascript"></a>delete 메서드(WeakMap)(JavaScript)
`WeakMap` 개체에서 지정된 요소를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
weakmapObj.delete(key)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `weakmapObj`  
 필수 요소. `WeakMap` 개체입니다.  
  
 `key`  
 필수 요소. 제거할 요소의 키입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 `true` 요소가 제거된 경우.  
  
## <a name="example"></a>예제  
 다음 예제에서는 멤버를 추가 하는 `WeakMap` 후 삭제 합니다.  
  
```JavaScript  
function Dog(breed) {  
    this.breed = breed;  
}  
  
var dog = new Dog("yorkie");  
  
var wm = new WeakMap();  
wm.set(dog, "fido");  
wm.delete(dog);  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]