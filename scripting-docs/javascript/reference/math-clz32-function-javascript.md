---
title: "Math.clz32 함수 (JavaScript) | Microsoft Docs"
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
ms.assetid: 34615d7a-6d88-4ab5-a696-7e496caa51db
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 511f407acc327a32ed6c53c12283503e20b514fe
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="mathclz32-function-javascript"></a>Math.clz32 함수(JavaScript)
숫자의 32비트 이진 표현에서 앞에 있는 0비트의 수를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Math.clz32(  
number  
)   
```  
  
## <a name="remarks"></a>설명  
 `number`이(가) 0이면 결과는 32가 됩니다. `number`의 32비트 이진 인코딩 중 최상위 비트가 1이면 결과는 0이 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **적용 대상**: [Math 개체](../../javascript/reference/math-object-javascript.md)