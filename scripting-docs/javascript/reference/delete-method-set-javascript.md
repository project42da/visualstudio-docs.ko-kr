---
title: "delete 메서드 (Set) (JavaScript) | Microsoft Docs"
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
ms.assetid: 052c409e-10c9-49f2-955d-5ad7e31c14f3
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 72762b93c6996fd72bd035c5d653f0e85f4ffd33
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="delete-method-set-javascript"></a>delete 메서드(Set)(JavaScript)
집합에서 지정된 된 요소를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
setObj.delete(value)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `setObj`  
 필수 요소. `Set` 개체입니다.  
  
 `value`  
 필수 요소. 제거할 요소입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 `true` 요소가 제거된 경우.  
  
## <a name="example"></a>예제  
 다음 예제에서는 멤버를 추가 하는 방법을 보여 줍니다는 `Set` 한 후 둘 중 하나를 삭제 합니다.  
  
```JavaScript  
var s = new Set();  
s.add("Thomas Jefferson");  
s.add(1776);  
s.add("founding father");  
s.delete("founding father");  
  
s.forEach(function (item) {  
    document.write(item.toString() + ", ");  
});  
  
// Output:  
// Thomas Jefferson, 1776,  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]