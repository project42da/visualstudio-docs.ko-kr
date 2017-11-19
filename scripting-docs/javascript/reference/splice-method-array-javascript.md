---
title: "splice 메서드 (Array) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: splice
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: splice method
ms.assetid: 85fdfb13-e3d9-4c89-b524-3ccee7001c93
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0d56a22244f76f5ce7221c276629907811733d51
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="splice-method-array-javascript"></a>splice 메서드(Array)(JavaScript)
배열에서 첫 번째 요소를 제거하고, 필요하면 그 자리에 새 요소를 삽입한 다음 삭제된 요소를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
arrayObj.splice(start, deleteCount, [item1[, item2[, . . . [,itemN]]]])  
```  
  
## <a name="parameters"></a>매개 변수  
 `arrayObj`  
 필수 요소. `Array` 개체입니다.  
  
 `start`  
 필수 요소. 배열에서 요소 제거를 시작 하는 0부터 시작 하는 위치입니다.  
  
 `deleteCount`  
 필수 요소. 제거할 요소의 수입니다.  
  
 `item1, item2,. . ., itemN`  
 선택 사항입니다. 대신 삭제 된 요소 배열에 삽입할 요소입니다.  
  
## <a name="remarks"></a>설명  
 `splice` 메서드 수정 `arrayObj` 위치에서 지정 된 개수의 요소를 제거 하 여 `start` 고 새 요소를 삽입 합니다. 삭제 된 요소는 새으로 반환 됩니다 `Array` 개체입니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `splice` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var arr = new Array("4", "11", "2", "10", "3", "1");  
arr.splice(2, 2, "21", "31");  
document.write(arr);  
  
// Output: 4,11,21,31,3,1  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [slice 메서드(Array)](../../javascript/reference/slice-method-array-javascript.md)