---
title: "get 메서드 (Map) (JavaScript) | Microsoft Docs"
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
ms.assetid: bebbd6bc-6e61-4674-8196-7e907798973f
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 243d5aa93289cb7a13b34567b7824d028151bad3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="get-method-map-javascript"></a>get 메서드(Map)(JavaScript)
맵에서 지정된 된 요소를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
mapObj.get(key)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mapObj`  
 필수 요소. `Map` 개체입니다.  
  
 `key`  
 필수 요소. 에 있는 요소의 키는 `Map`합니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 키와 연결 된 개체를 반환 합니다. 경우는 `Map` 에 없는 키를이 메서드는 반환 된 `undefined` 값입니다.  
  
## <a name="example"></a>예제  
 요소를 검색 하는 방법을 보여 주는 다음 예제는 `Map` 개체입니다.  
  
```JavaScript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
  
document.write(m.get(2));  
  
// Output:  
// red  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]