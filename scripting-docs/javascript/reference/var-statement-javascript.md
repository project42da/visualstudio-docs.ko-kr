---
title: "var 문 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/22/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: var_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- declaring variables, var statement
- var statement
ms.assetid: 56f900af-a5c4-4667-9664-5956d30f0aae
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 839b6904fa59b6f4ea9a5c4d8e00213cd351517a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="var-statement-javascript"></a>var 문(JavaScript)
변수를 선언합니다.  
  
## <a name="syntax"></a>구문  
  
```  
var variable1 = value1  
```  
  
## <a name="parameters"></a>매개 변수  
 `variable1`  
 선언 되는 변수의 이름입니다.  
  
 `value1`  
 변수에 할당 된 초기 값입니다.  
  
## <a name="remarks"></a>설명  
 사용 된 `var` 변수를 선언 하는 문입니다. 선언할 때 변수 또는 나중에 스크립트 값을 할당할 수 있습니다.  
  
 변수가 처음으로 선언 된 스크립트에 표시 합니다.  
  
 사용 하지 않고 변수를 선언할 수는 `var` 키워드와 값을 지정 합니다. 로 알려져 있는 *암시적 선언을*, 권장 되지 않습니다. 암시적 선언에서 변수 글로벌 범위를 제공합니다. 프로시저 수준에서 변수를 선언할 때 하지만 일반적으로 원하지 않는 전역 범위에 있어야 합니다. 방지 하기 위해 변수 글로벌 범위를 사용 해야 합니다는 `var` 변수 선언에서 키워드입니다.  
  
 변수를 초기화 하지 않는 경우는 `var` 문을 자동으로 할당 됩니다는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 값 `undefined`합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 사용을 보여 주기는 `var` 문.  
  
```JavaScript  
var index;  
var name = "Thomas Jefferson";  
var answer = 42, counter, numpages = 10;  
var myarray = new Array();  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [function 문](../../javascript/reference/function-statement-javascript.md)   
 [new 연산자](../../javascript/reference/new-operator-decrementjavascript.md)   
 [Array 개체](../../javascript/reference/array-object-javascript.md)   
 [변수](../../javascript/variables-javascript.md)