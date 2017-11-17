---
title: "const 문 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: const_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- declaring variables, const statement
- const statement
ms.assetid: 3ad0840f-437f-4163-9571-86ecc5ddb987
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 68130cec4f1b1fe89d2fe3e673b28963d79aebde
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="const-statement-javascript"></a>const 문(JavaScript)
상수 값을 사용하여 블록 범위 변수를 선언합니다.  
  
## <a name="syntax"></a>구문  
  
```  
const constant1 = value1  
```  
  
#### <a name="parameters"></a>매개 변수  
 `constant1`  
 선언 되는 변수의 이름입니다.  
  
 `value1`  
 변수에 할당 된 초기 값입니다.  
  
## <a name="remarks"></a>설명  
 사용 하 여는 `const` 있는 범위는 블록에 제한 된 상수 값을 사용 하 여 변수를 선언 하는 문을 자신이 선언에 있습니다. 변수의 값을 변경할 수 없습니다.  
  
 선언 된 변수를 사용 하 여 `const` 선언할 때 초기화 되어야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제는 `const` 문의 사용 예를 보여줍니다.  
  
```JavaScript  
var c = 10;  
{  
    const c = 2;  
   // At this point, c = 2.  
}  
// At this point, c = 10.  
  
// Additional ways to declare a variable using const.  
const name = "Thomas Jefferson";  
const answer = 42, numpages = 10;  
const myarray = new Array();  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [let 문](../../javascript/reference/let-statement-javascript.md)   
 [new 연산자](../../javascript/reference/new-operator-decrementjavascript.md)   
 [Array 개체](../../javascript/reference/array-object-javascript.md)   
 [변수](../../javascript/variables-javascript.md)