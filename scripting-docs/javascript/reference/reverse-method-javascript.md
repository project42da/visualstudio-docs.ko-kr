---
title: "reverse 메서드 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: reverse
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- arrays [Visual Studio], reversing elements
- reverse method
- transposing elements
ms.assetid: 02ab051b-79b8-4646-b502-381671e78c12
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9a34385ccf89557688698b50384b3dfe359478df
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="reverse-method-javascript"></a>reverse 메서드(JavaScript)
요소를 예약 된 `Array`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
arrayObj.reverse()   
```  
  
## <a name="parameters"></a>매개 변수  
 `arrayObj`  
 필수 요소. 모든 `Array` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 역방향된 배열입니다.  
  
## <a name="remarks"></a>설명  
 필요한 `arrayObj` 참조가 `Array` 개체입니다.  
  
 `reverse` 의 요소를 예약 하는 메서드는 `Array` 위치에서 개체입니다. 문제가 발생 하지 않는 새 `Array` 실행 하는 동안 개체입니다.  
  
 배열이 인접는 `reverse` 메서드 배열에서 간격을 채우는 배열에 요소를 만듭니다. 값이 요소를 생성 합니다. 이러한 각 `undefined`합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `reverse` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var arr = new Array(0,1,2,3,4);   
var reverseArr = arr.reverse();  
document.write(reverseArr);  
  
// Output:  
// 4,3,2,1,0  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [concat 메서드(Array)](../../javascript/reference/concat-method-array-javascript.md)