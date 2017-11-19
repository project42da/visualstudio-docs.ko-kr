---
title: "Math.round 함수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: round
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Round method
- Math object
ms.assetid: 51008df3-5d0c-4951-84cb-4f41000db0be
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9543d529e3d0e4e45cff29f1286edbfad8dc0e27
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="mathround-function-javascript"></a>Math.round 함수(JavaScript)
가장 가까운 정수로 반올림 된 제공된 된 숫자 식을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Math.round(  
number  
)   
```  
  
## <a name="remarks"></a>설명  
 필요한 `number` 인수는 가장 가까운 정수로 반올림 되는 값입니다.  
  
 양수에 대 한 경우의 소수 부분이 `number` 0.5 이상이 반환 값은 보다 큰 가장 작은 정수 같지 `number`합니다. 소수 부분이 0.5 보다 작은 경우 반환 값이 최대 정수 보다 작거나 `number`합니다.  
  
 음수 소수 부분이 정확 하 게 하는 경우에 대 한-0.5, 반환 값은 숫자 보다 큰 가장 작은 정수입니다.  
  
 예를 들어 `Math.round(8.5)` 9를 반환 하지만 `Math.round(-8.5)` -8을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Math 개체](../../javascript/reference/math-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [Math.random 함수](../../javascript/reference/math-random-function-javascript.md)