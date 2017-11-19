---
title: "Number.isInteger 함수 (Number) (JavaScript) | Microsoft Docs"
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
ms.assetid: 54fcf68c-0067-4bad-af94-d7ff8c88914a
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 20e1b7b463003d3a25ef64bba793b3273371266b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="numberisinteger-function-number-javascript"></a>Number.isInteger 함수(Number)(JavaScript)
값이 정수인지 여부를 나타내는 부울 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Number.isInteger(numValue)   
```  
  
## <a name="return-value"></a>반환 값  
 값이 정수이면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **적용 대상**: [개체 번호](../../javascript/reference/number-object-javascript.md)  
  
## <a name="example"></a>예제  
  
```JavaScript  
// Returns true  
Number.isInteger(100)  
Number.isInteger(-100)  
  
// Returns false  
Number.isInteger(Number.NaN)  
Number.isInteger(Infinity)  
Number.isInteger(100 / 3)  
Number.isInteger("100")  
  
```