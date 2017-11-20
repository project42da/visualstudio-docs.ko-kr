---
title: "WeakSet 개체 (JavaScript) | Microsoft Docs"
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
ms.assetid: f97e6e7c-d678-4e32-978e-d949a7cafa3a
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e42849c03f698d6ed5f8b0e28725c85555a74d2b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="weakset-object-javascript"></a>WeakSet 개체(JavaScript)
임의의 형식일 수 있는 고유 개체 컬렉션입니다.  
  
## <a name="syntax"></a>구문  
  
```  
setObj = new WeakSet()  
```  
  
## <a name="remarks"></a>설명  
 고유하지 않은 개체를 `WeakSet`에 추가하려는 경우 새 개체가 컬렉션에 추가되지 않습니다.  
  
 `Set`와 달리 개체만 컬렉션에 추가할 수 있습니다. 임의의 값은 컬렉션에 추가할 수 없습니다.  
  
 에 `WeakSet` 개체 집합의 개체에 대 한 참조는 '약하게' 유지 됩니다. 즉, `WeakSet`는 개체에서 가비지 컬렉션이 발생하지 않도록 방지하지 않습니다. 개체에 대한 참조가 없는 경우(`WeakSet` 이외)에는 가비지 수집기가 개체를 수집할 수 있습니다.  
  
 `WeakSet`(또는 `WeakMap`)는 개체 또는 개체 메타데이터의 캐싱을 포함하는 일부 시나리오에 유용할 수 있습니다. 예를 들어 확장할 수 없는 개체에 대한 메타데이터는 `WeakSet`에 저장하거나 `WeakSet`를 사용하여 사용자 이미지의 캐시를 만들 수 있습니다.  
  
## <a name="properties"></a>속성  
 다음 표에서는 `WeakSet` 개체의 속성을 보여 줍니다.  
  
|속성|설명|  
|--------------|-----------------|  
|생성자|집합을 만드는 함수를 지정합니다.|  
|프로토타입|집합의 프로토타입에 대한 참조를 반환합니다.|  
  
## <a name="methods"></a>메서드  
 다음 표에서는 `WeakSet` 개체의 메서드를 보여 줍니다.  
  
|메서드|설명|  
|------------|-----------------|  
|추가|집합에 요소를 추가합니다.|  
|삭제|집합에서 지정된 요소를 제거합니다.|  
|has는|집합에 지정된 요소가 포함된 경우 `true`를 반환합니다.|  
  
## <a name="example"></a>예제  
 다음 예제에는 멤버를 집합에 추가한 다음 추가되었는지 확인하는 방법을 보여 줍니다.  
  
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