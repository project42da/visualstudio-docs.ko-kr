---
title: "toString 메서드 (Array) | Microsoft Docs"
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
ms.assetid: 71fbea85-3e00-41b0-b167-25e4281e5e8a
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6dc7cbf843e47ffc2d21f5a2b1d03c43e675a130
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="tostring-method-array"></a>toString 메서드(Array)
배열을 나타내는 문자열을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
array.toString()  
```  
  
## <a name="parameters"></a>매개 변수  
 `array`  
 필수 요소. 나타내는 문자열 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 배열의 문자열 표현입니다.  
  
## <a name="remarks"></a>설명  
 요소는 `Array` 문자열로 변환 됩니다. 결과 문자열은 연결 되 고 쉼표로 구분 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **toString** 메서드는 배열입니다.  
  
```JavaScript  
var arr = [1, 2, 3, 4];  
var s = arr.toString();  
document.write(s);  
  
// Output: 1,2,3,4  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]