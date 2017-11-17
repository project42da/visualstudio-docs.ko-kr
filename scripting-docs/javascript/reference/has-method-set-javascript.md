---
title: "has 메서드 (Set) (JavaScript) | Microsoft Docs"
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
ms.assetid: fb80f2e0-fc5e-4508-af14-1c3b3b833636
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c9690e3d091e8ae0f9670fd737a29590524834c9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="has-method-set-javascript"></a>has 메서드(Set)(JavaScript)
반환 `true` 집합에 지정된 된 요소입니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
setObj.has(value)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `setObj`  
 필수 요소. `Set` 개체입니다.  
  
 `value`  
 필수 요소. 테스트할 요소입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 집합이 지정된 요소를 포함하는 경우 `true`입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 멤버를 `Set`에 추가한 다음 집합에 특정 멤버가 포함되는지 여부를 확인하는 방법을 보여 줍니다.  
  
```JavaScript  
var s = new Set();  
s.add("Thomas Jefferson");  
s.add(1776);  
  
document.write(s.has(1776));  
document.write(s.has("1776"));  
  
// Output:  
// true  
// false  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]