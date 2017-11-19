---
title: "Number.isFinite 함수 (Number) (JavaScript) | Microsoft Docs"
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
ms.assetid: 41a91408-09d1-49f2-b7a0-6da105e2ed8e
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c23ff1e80ad71fd9d848f7a0e33628131f5d8014
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="numberisfinite-function-number-javascript"></a>Number.isFinite 함수(Number)(JavaScript)
값을 한정 숫자인지 여부를 나타내는 부울 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Number.isFinite(numValue)   
```  
  
## <a name="return-value"></a>반환 값  
 값이 `NaN`, `+∞` 또는 `-∞`이면 `false`이고, 그렇지 않으면 `true`입니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예제  
  
```JavaScript  
// Returns true  
Number.isFinite(100)  
Number.isFinite(-100)  
Number.isFinite(100 / 3)  
  
// Returns false  
Number.isFinite(Number.NaN)  
Number.isFinite(Infinity)  
Number.isFinite("100")  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **적용 대상**: [개체 번호](../../javascript/reference/number-object-javascript.md)