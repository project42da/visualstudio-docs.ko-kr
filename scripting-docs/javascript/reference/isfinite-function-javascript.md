---
title: "isFinite 함수 (JavaScript) | Microsoft Docs"
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
- isFinite
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- finite numbers
- isFinite method
ms.assetid: ea9287d2-892f-496b-86b7-f9196868d5cf
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ce78afe59190a03fb079841e7691f84c01eebedd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="isfinite-function-javascript"></a>isFinite 함수(JavaScript)
제공 된 숫자 유한 인지 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
isFinite(number)   
```  
  
## <a name="remarks"></a>설명  
 필요한 `number` 인수는 숫자 값입니다.  
  
 `isFinite` 함수에서 반환 `true` 경우 `number` 아닌 다른 값이 `NaN`, 양의 무한대 또는 음의 무한대 합니다. 이러한 세 가지 경우에서 반환 **false**합니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [전역 개체](../../javascript/reference/global-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [isNaN 함수](../../javascript/reference/isnan-function-javascript.md)