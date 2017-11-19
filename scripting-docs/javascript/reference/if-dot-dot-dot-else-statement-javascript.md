---
title: "if... else 문 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- else_JavaScriptKeyword
- if_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- if statement, if...else
- loop structures, if...else statements
ms.assetid: dfbe86e8-9c1e-4ef5-bb9c-7d1db7ce2506
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fad12b970f69a15040acb59195f957a2a6eec3e0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ifelse-statement-javascript"></a>if...else 문(JavaScript)
식의 값에 따라 문 그룹을 조건부로 실행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
if (condition1) {  
    statement1  
}  
[else if (condition2) {  
    statement2  
}]  
[else {  
    statement3]   
}]  
```  
  
## <a name="parameters"></a>매개 변수  
 `condition1`  
 필수 요소. 부울 식입니다. 경우 `condition1` 은 `null` 또는 `undefined`, `condition1` 로 처리 `false`합니다.  
  
 `statement1`  
 선택 사항입니다. 될 경우 실행할 문을 `condition1` 은 **true**합니다. 복합 문일 수 있습니다.  
  
 `condition2`  
 평가할 조건입니다.  
  
 `statement2`  
 선택 사항입니다. 될 경우 실행할 문을 `condition2` 은 `true`합니다. 복합 문일 수 있습니다.  
  
 `statement3`  
 두 `condition1` 및 `condition2` 는 `false`,이 문을 실행 합니다.  
  
## <a name="example"></a>예제  
 다음 코드를 사용 하는 방법을 보여 줍니다 `if`, `if else`, 및 `else`합니다.  
  
 것이 좋습니다을 묶는 `statement1` 및 `statement2` 쉽게 구별할 수 있도록 하 고 의도 하지 않은 오류를 방지 하려면 중괄호 ({}).  
  
```JavaScript  
var z = 3;  
if (x == 5) {  
    z = 10;  
}  
else if (x == 10) {  
    z = 15;  
}  
else {  
    z = 20;  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [조건부(삼항) 연산자(?:)](../../javascript/reference/conditional-ternary-operator-decrement-javascript.md)