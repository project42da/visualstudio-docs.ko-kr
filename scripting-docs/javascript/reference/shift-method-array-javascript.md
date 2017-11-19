---
title: "shift 메서드 (Array) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: shift
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: shift method
ms.assetid: f33baec5-f67e-4760-b7c1-553727bd0423
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 664c3f764950b329cea8356f5b350ee917f0a60f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="shift-method-array-javascript"></a>shift 메서드(Array)(JavaScript)
배열에서 첫 번째 요소를 제거하여 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
arrayObj.shift( )  
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `arrayObj` 참조가 `Array` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 배열에서 제거 되는 요소를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 다음 예제에서는 `shift` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var arr = new Array(10, 11, 12);  
while (arr.length > 0)  
    {  
    var i = arr.shift();  
    document.write (i.toString() + " ");  
    }  
  
// Output:   
// 10 11 12  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [unshift 메서드(Array)](../../javascript/reference/unshift-method-array-javascript.md)