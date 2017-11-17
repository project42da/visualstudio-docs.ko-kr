---
title: "forEach 메서드 (Set) (JavaScript) | Microsoft Docs"
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
ms.assetid: 813bff6e-6098-4260-ab6e-b0d2da6be94d
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b89c56b54fd74c25c43a84f2f0fd68922aa9f637
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="foreach-method-set-javascript"></a>forEach 메서드(Set)(JavaScript)
집합의 각 요소에 대해 지정된 된 작업을 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
setObj.forEach(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>매개 변수  
 `setObj`  
 필수 요소. `Set` 개체입니다.  
  
 `callbackfn`  
 필수 요소. `callbackfn`최대 3 개의 인수를 허용합니다. 함수는 `forEach` 집합의 각 요소에 대해 한 번 호출 합니다.  
  
 `thisArg`  
 선택 사항입니다. 개체는는 `this` 키워드에 결과를 참조할 수는 `callbackfn` 함수입니다. `thisArg`가 생략되면 `undefined`가 `this` 값으로 사용됩니다.  
  
## <a name="exceptions"></a>예외  
 `callbackfn` 인수가 함수 개체가 아닌 경우 `TypeError` 예외가 throw됩니다.  
  
## <a name="remarks"></a>설명  
 호출 함수의 구문은 다음과 같습니다.  
  
 `function callbackfn(value, key, setObj)`  
  
 다음 표에 나와 있는 것 처럼 최대 3 개의 매개 변수를 사용 하 여 콜백 함수를 선언할 수 있습니다.  
  
|콜백 인수|정의|  
|-----------------------|----------------|  
|`value`|집합에 포함 하는 값입니다.|  
|`key`|집합에 포함 하는 값입니다. 집합 키가 없는이 값은 동일 하므로 `value`합니다.|  
|`setObj`|`Set` 를 트래버스해야 하는 개체입니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 `forEach`을 사용하는 방법을 보여 줍니다. `callbackfn` 인수에 콜백 함수의 코드가 포함 되어 있습니다.  
  
```JavaScript  
var s = new Set();  
  
s.add("scale");  
s.add(10);  
s.add("5");  
  
s.forEach(function(item, sameItem, s) {  
    document.write("Size of the set object is: " + s.size + "<br />");  
    document.write("Deleting item: " + item + "<br />");  
    s.delete(sameItem);  
});  
  
// Output:  
// Size of the set object is: 3  
// Deleting item: scale  
// Size of the set object is: 2  
// Deleting item: 10  
// Size of the set object is: 1  
// Deleting item: 5  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 있는지 검색할 수도 있습니다 멤버 집합에서 하나의 매개 변수만 콜백 함수에 전달 하 여 보여 줍니다.  
  
```JavaScript  
var s = new Set();  
s.add("Thomas Jefferson");  
s.add(1776);  
s.add("founding father");  
  
s.forEach(function (item) {  
    document.write(item.toString() + ", ");  
});  
  
// Output:  
// Thomas Jefferson, 1776, founding father,  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]