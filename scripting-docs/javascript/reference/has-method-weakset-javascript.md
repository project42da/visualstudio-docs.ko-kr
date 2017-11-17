---
title: "has 메서드 (WeakSet) (JavaScript) | Microsoft Docs"
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
ms.assetid: e24f0876-26bd-4007-b12a-360bb6fa0951
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0dbc7e17e3fd73730386293c5e3f894455e41a93
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="has-method-weakset-javascript"></a>has 메서드(WeakSet)(JavaScript)
`WeakSet`가 지정된 요소를 포함하는 경우 `true`를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
setObj.has(obj)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `setObj`  
 필수 요소. `WeakSet` 개체입니다.  
  
 `obj`  
 필수 요소. 테스트할 요소입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 집합이 지정된 요소를 포함하는 경우 `true`입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 멤버를 `WeakSet`에 추가한 다음 집합에 특정 멤버가 포함되는지 여부를 확인하는 방법을 보여 줍니다.  
  
```JavaScript  
var ws = new WeakSet();  
  
var str = new String("Thomas Jefferson");  
var num = new Number(1776);  
  
ws.add(str);  
ws.add(num);  
  
console.log(ws.has(str));  
console.log(ws.has(num));  
  
ws.delete(str);  
console.log(ws.has(str));  
  
// Output:  
// true  
// true  
// false  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]