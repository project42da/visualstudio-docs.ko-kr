---
title: "delete 메서드 (WeakSet) (JavaScript) | Microsoft Docs"
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
ms.assetid: 19e93366-7d42-4abf-b7b9-fcf943fa17a3
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 46eeac8ddd0072712c1867bc2a419a4e3255ffd6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="delete-method-weakset-javascript"></a>delete 메서드(WeakSet)(JavaScript)
`WeakSet`에서 지정된 요소를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
weaksetObj.delete(obj)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `weaksetObj`  
 필수 요소. `WeakSet` 개체입니다.  
  
 `obj`  
 필수 요소. 제거할 요소입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 `true` 요소가 제거된 경우.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `WeakSet`의 요소를 추가 및 삭제하는 방법을 보여줍니다.  
  
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