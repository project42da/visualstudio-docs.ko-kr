---
title: "while 문 (JavaScript) | Microsoft Docs"
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
- while_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- loop structures, while statements
- while statement
ms.assetid: d63777cf-0e1a-4555-8d3a-334381001f48
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: de64bf9181a0fc86a528fa7af21216b99530f217
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="while-statement-javascript"></a>while 문(JavaScript)
지정 된 조건이 될 때까지 문 또는 일련의 문 실행 `false`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
while (expression) {  
    statements  
}   
```  
  
## <a name="parameters"></a>매개 변수  
 `expression`  
 필수 요소. 루프의 각 반복 전에 체크 인 된 부울 식입니다. 경우 `expression` 은 `true`, 루프가 실행 된 합니다. 경우 `expression` 은 `false`, 루프 종료 됩니다.  
  
 `statements`  
 선택적 요소. 될 경우 실행할 하나 이상의 문을 `expression` 은 `true`합니다.  
  
## <a name="remarks"></a>설명  
 `while` 문 검사 `expression` 루프를 처음 실행 하기 전에. 경우 `expression` 은 `false` 이번에 루프 실행 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제는 `while` 문의 사용 예를 보여줍니다.  
  
```JavaScript  
var i = 0;  
var j = 10;  
while (i < 100) {  
    if (i == j)  
        break;  
    i++;  
}  
document.write(i);  
  
// Output: 10  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [break 문](../../javascript/reference/break-statement-javascript.md)   
 [continue 문](../../javascript/reference/continue-statement-javascript.md)   
 [do...while 문](../../javascript/reference/do-dot-dot-dot-while-statement-javascript.md)   
 [for 문](../../javascript/reference/for-statement-javascript.md)   
 [for...in 문](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)