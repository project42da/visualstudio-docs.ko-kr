---
title: "has 메서드 (Map) (JavaScript) | Microsoft Docs"
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
ms.assetid: 876df854-2941-4db2-92c6-1b497840b169
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 48228b495c845bef91caa0b85e67980100a6f790
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="has-method-map-javascript"></a>has 메서드(Map)(JavaScript)
반환 `true` 맵에 지정된 된 요소를 포함 하는 경우.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
mapObj.has(key)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mapObj`  
 필수 요소. `Map` 개체입니다.  
  
 `key`  
 필수 요소. 테스트 하는 요소의 키입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 `true`지도 포함 된 경우 지정된 된 요소.  
  
## <a name="example"></a>예제  
 다음 예제에서는 멤버를 추가 하는 방법을 보여 줍니다는 `Map` 다음 맵을 포함 여부를 확인 합니다.  
  
```JavaScript  
var m = new Map();  
m.set(2, "red");  
  
document.write(m.has(2));  
  
// Output:  
// true  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]