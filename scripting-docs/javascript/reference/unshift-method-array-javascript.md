---
title: "unshift 메서드 (Array) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- unshift
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- unshift method
ms.assetid: 8c6a39ed-bab3-4ca4-9350-571a9427ec94
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c3f0d210514d04afa5cf467819a5e843925e1a68
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="unshift-method-array-javascript"></a>unshift 메서드(Array)(JavaScript)
배열 시작에 새 요소를 삽입합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
arrayObj.unshift([item1[, item2 [, . . . [, itemN]]]])  
```  
  
## <a name="parameters"></a>매개 변수  
 `arrayObj`  
 필수 요소. `Array` 개체입니다.  
  
 `item1, item2,. . ., itemN`  
 선택 사항입니다. 시작 부분에 삽입할 요소는 `Array`합니다.  
  
## <a name="remarks"></a>설명  
 `unshift` 메서드 인수 목록에 표시 되는 동일한 순서로 표시 배열의 시작 부분에 요소를 삽입 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `unshift` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var ar = new Array();  
ar.unshift(10, 11);  
ar.unshift(12, 13, 14);  
document.write(ar.toString());  
  
// Output: 12,13,14,10,11  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [shift 메서드(Array)](../../javascript/reference/shift-method-array-javascript.md)