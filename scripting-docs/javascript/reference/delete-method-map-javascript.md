---
title: "delete 메서드 (Map) (JavaScript) | Microsoft Docs"
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
ms.assetid: a073e1a1-5862-485b-b2bd-26c66a3aff51
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5185b883cf603acdc91fe1f1c833d337c4468ba4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="delete-method-map-javascript"></a>delete 메서드(Map)(JavaScript)
지도에서 지정된 된 요소를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
mapObj.delete(key)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mapObj`  
 필수 요소. `Map` 개체입니다.  
  
 `key`  
 필수 요소. 제거할 요소의 키입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 `true` 요소가 제거된 경우.  
  
## <a name="example"></a>예제  
 다음 예제에서는 멤버를 추가 하는 방법을 보여 줍니다는 `Map` 한 후 둘 중 하나를 삭제 합니다.  
  
```JavaScript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
m.delete(1);  
  
m.forEach(function (item) {  
    document.write(item.toString() + "<br />");  
});  
  
// Output:  
// red  
// 2  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]