---
title: "toString 메서드 (Boolean) 1 | Microsoft Docs"
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
ms.assetid: c46b43c0-6946-407a-b0e0-49cba90e226a
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 17dd9503e4e09aafca3d153662bf7487538cda3d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="tostring-method-boolean-1"></a>toString 메서드 (Boolean) 1
개체를 나타내는 문자열을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
boolean.toString()  
```  
  
## <a name="parameters"></a>매개 변수  
 `boolean`  
 필수 요소. 대 한 문자열 표현을 가져올 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 부울 값이 `true`을 "true"를 반환 합니다. 그렇지 않으면 "false"를 반환합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예제  
 다음 예제에서는 **toString** 메서드.  
  
```JavaScript  
var s = new Boolean(0);  
document.write(s.toString());  
  
// Output: false;  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]