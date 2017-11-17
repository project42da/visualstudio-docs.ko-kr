---
title: "let 문 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: let_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- let statement
- declaring variables, let statement
ms.assetid: c7e4f8a9-8f54-47b6-aed2-956959c1ecfd
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c447a1bf0c430771ff146965a592f7e160e2055b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="let-statement-javascript"></a>let 문(JavaScript)
블록 범위 변수를 선언합니다.  
  
## <a name="syntax"></a>구문  
  
```  
let variable1 = value1  
```  
  
#### <a name="parameters"></a>매개 변수  
 `variable1`  
 선언 되는 변수의 이름입니다.  
  
 `value1`  
 변수에 할당 된 초기 값입니다.  
  
## <a name="remarks"></a>설명  
 사용 하 여는 `let` 있는 범위는 블록에 제한 된 변수를 선언 하는 문을 자신이 선언에 있습니다. 선언할 때 변수 또는 나중에 스크립트 값을 할당할 수 있습니다.  
  
 선언 된 변수를 사용 하 여 `let` 을 사용할 수 전에 선언 또는 오류가 발생 합니다.  
  
 변수를 초기화 하지 않는 경우는 `let` 문을 자동으로 할당 됩니다는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 값 `undefined`합니다.  
  
## <a name="example"></a>예제  
 다음 예제는 `let` 문의 사용 예를 보여줍니다.  
  
```JavaScript  
var  l = 10;  
{  
    let l = 2;  
   // At this point, l = 2.  
}  
// At this point, l = 10.  
  
// Additional ways to declare a variable using let.  
let index;  
let name = "Thomas Jefferson";  
let answer = 42, counter, numpages = 10;  
let myarray = new Array();  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [const 문](../../javascript/reference/const-statement-javascript.md)   
 [new 연산자](../../javascript/reference/new-operator-decrementjavascript.md)   
 [Array 개체](../../javascript/reference/array-object-javascript.md)   
 [변수](../../javascript/variables-javascript.md)