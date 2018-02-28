---
title: "caller 속성 (Function) (JavaScript) | Microsoft Docs"
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
- caller
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- caller property
- function calls, functions that are executing
ms.assetid: ae210853-7160-4102-9cfd-ab489f180ce1
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8c6eef1b8304612c2ed16a4cc389bf3b2a28b70f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="caller-property-function-javascript"></a>caller 속성(Function)(JavaScript)
현재 함수를 호출 하는 함수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
functionName.caller  
```  
  
## <a name="remarks"></a>설명  
 `functionName` 함수 실행의 이름을 개체입니다.  
  
 `caller` 함수가 실행 중인 동안에 함수에 대 한 속성은 정의 합니다. 함수가 수준의 위쪽에서 호출 되는 경우는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 프로그램 `caller` 포함 `null`합니다.  
  
 경우는 `caller` 속성 문자열 컨텍스트에서 사용 되는, 결과 동일 `functionName`.`toString`, 즉, 함수의 디컴파일된 텍스트가 표시 됩니다.  
  
 다음 예제에서는 `caller` 속성을 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
function CallLevel(){  
   if (CallLevel.caller == null)  
      return("CallLevel was called from the top level.");  
   else  
      return("CallLevel was called by another function.");  
}  
  
document.write(CallLevel());  
  
// Output: CallLevel was called from the top level.  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [function 문](../../javascript/reference/function-statement-javascript.md)