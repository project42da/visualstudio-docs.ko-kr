---
title: "has 메서드 (WeakMap) (JavaScript) | Microsoft Docs"
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
ms.assetid: 12bedca1-bde7-413a-a4e2-06c03559044f
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e9a1706a1b96b5273ec280c4cef2be47a3bc6e17
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="has-method-weakmap-javascript"></a>has 메서드(WeakMap)(JavaScript)
반환 `true` 경우는 `WeakMap` 개체에 지정된 된 요소가 포함 되어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
weakmapObj.has(key)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `weakmapObj`  
 필수 요소. `WeakMap` 개체입니다.  
  
 `key`  
 필수 요소. 테스트 하는 요소의 키입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 `true`경우는 `WeakMap` 지정된 된 키를 포함 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 멤버를 추가 하는 방법을 보여 줍니다는 `WeakMap` 다음 사용 하 여 `has` 존재 하는지 여부를 확인 합니다.  
  
```JavaScript  
var dog = {  
    breed: "yorkie"  
}  
  
var wm = new WeakMap();  
wm.set(dog, "fido");  
  
document.write(wm.has(dog));  
  
// Output:  
// true  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]