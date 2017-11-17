---
title: "Object.is 함수 (JavaScript) | Microsoft Docs"
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
ms.assetid: 6e2f6c6d-7cd2-47c4-a513-3ba53988d27d
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 36d4c281fdafbfacb0b1f6061ef4a90bfac99234
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="objectis-function-javascript"></a>Object.is 함수(JavaScript)
두 값이 같은 값인지를 나타내는 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
Object.is(value1, value2)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `value1`  
 필수 요소. 테스트할 첫 번째 값입니다.  
  
 `value2`  
 필수 요소. 테스트할 두 번째 값입니다.  
  
## <a name="return-value"></a>반환 값  
 값이 동일한 값이면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## <a name="remarks"></a>설명  
 == 연산자와 달리 `Object.is`는 값을 테스트할 때 형식을 강제 변환하지 않습니다.  
  
 `Object.is`에 의해 적용되는 비교는 `Object.is`가 `Number.isNaN`을 `NaN`과 동일한 값으로 처리한다는 점을 제외하고 === 연산자에 의해 적용되는 비교와 유사합니다. +0과 -0도 다른 값으로 처리합니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]