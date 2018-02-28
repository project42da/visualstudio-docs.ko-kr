---
title: "join 메서드 (Array) (JavaScript) | Microsoft Docs"
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
- join
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Join method
- concatenating strings, join method
- arrays [Visual Studio], joining
ms.assetid: 20f8fde1-014b-488e-9008-464a86e6b21f
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4591b12b3556384fef3e367d20cf9545d2f3dedd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="join-method-array-javascript"></a>join 메서드(Array)(JavaScript)
지정 된 구분 기호 문자열에 의해 구분 된 배열의 모든 요소를 추가 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
arrayObj.join([separator])   
```  
  
## <a name="parameters"></a>매개 변수  
 `arrayObj`  
 필수 요소. `Array` 개체입니다.  
  
 `separator`  
 선택 사항입니다. 결과에서 다음에서 배열의 한 요소를 구분 하는 데 필요한 문자열 `String`합니다. 생략 하는 경우 배열 요소는 쉼표로 구분 됩니다.  
  
## <a name="remarks"></a>설명  
 배열의 모든 요소가 있으면 **정의 되지 않은** 또는 `null`을 빈 문자열로 취급 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **조인** 메서드.  
  
```JavaScript  
var a, b;  
a = new Array(0,1,2,3,4);  
b = a.join("-");  
document.write(b);  
  
// Output:  
// 0-1-2-3-4  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [String 개체](../../javascript/reference/string-object-javascript.md)