---
title: "do...while 문 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: do_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- do...while statement
- terminating loops
- loop structures, do and do-while
ms.assetid: 8b7782ba-fbad-48cd-9639-193566da6ae5
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 895d98a3de3a6691ce60bf0456bb838403619f88
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="dowhile-statement-javascript"></a>do...while 문(JavaScript)
문 블록을 한 번 실행 한 후 반복 루프의 실행을 조건 식이 평가 될 때까지 `false`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
do {  
    statement  
}  
while (expression) ;   
```  
  
## <a name="parameters"></a>매개 변수  
 `statement`  
 필수 요소. 될 경우 실행할 문을 `expression` 은 `true`합니다. 복합 문일 수 있습니다.  
  
 `expression`  
 필수 요소. Boolean으로 강제 변환할 수 있는 식 `true` 또는 `false`합니다. 경우 `expression` 은 `true`, 루프를 다시 실행 됩니다. 경우 `expression` 은 `false`, 루프 종료 됩니다.  
  
## <a name="remarks"></a>설명  
 와 달리는 `while` 문는 `do...while` 루프에는 조건식이 계산 되기 전에 한 번 실행 됩니다.  
  
 줄는 `do...while` 블록을 사용할 수 있습니다는 `break` 문을 프로그램 흐름, 루프 또는 있습니다 사용할 수는 `continue` 문 바로 이동할 수는 `while` 식입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 문은 `do...while` 루프 계속 실행 하는 동안 변수 `i` 이 10 보다 작은 합니다.  
  
```JavaScript  
var i = 0;  
do {  
    document.write(i + " ");  
    i++;  
} while (i < 10);  
  
// Output: 0 1 2 3 4 5 6 7 8 9   
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 루프 내의 문이 조건이 충족 되지 않으면 경우에 한 번 실행 됩니다.  
  
```JavaScript  
var i = 10;  
do {  
    document.write(i + " ");  
    i++;  
} while (i < 10);  
  
// Output: 10  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [break 문](../../javascript/reference/break-statement-javascript.md)   
 [continue 문](../../javascript/reference/continue-statement-javascript.md)   
 [for 문](../../javascript/reference/for-statement-javascript.md)   
 [>for.. 문에서](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [while 문](../../javascript/reference/while-statement-javascript.md)   
 [Labeled 문](../../javascript/reference/labeled-statement-javascript.md)