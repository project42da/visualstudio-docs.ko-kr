---
title: "break 문 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: break_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- do...while statement
- break statement
ms.assetid: 5be0f2a8-5fe7-4a6c-89af-ca20a925ce87
caps.latest.revision: "23"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5f085a4e51309bf9a060e9ffa352c6ae85924237
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="break-statement-javascript"></a>break 문(JavaScript)
현재 루프 또는 함께 사용 된 경우 종료는 `label`, 연결된 된 문을 종료 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
break [label];  
```  
  
## <a name="remarks"></a>설명  
 선택적 `label` 인수에서 중단할 문의의 레이블을 지정 합니다.  
  
 일반적으로 사용는 `break` 문에서 `switch` 문 및 `while`, `for`, `for...in`, 또는 `do...while` 루프입니다. 가장 일반적으로 사용 하는 `label` 인수 `switch` 문, 하지만 그 단순 문이나 복합 모든 문에서 사용할 수 있습니다.  
  
 실행 된 `break` 문을 현재 루프 또는 문을가 끝내 고 바로 다음 문으로 시작 하는 스크립트를 실행 합니다.  
  
## <a name="examples"></a>예제  
 이 예에서 카운터 1에서 99 사이로; 계산 설정 됩니다. 그러나는 `break` 문은 14 개수 후 루프를 종료 합니다.  
  
```JavaScript  
for (var i = 1; i < 100; i++) {  
    if (i == 15) {  
        break;  
    }  
    document.write (i);  
    document.write (" ");  
}  
  
// Output: 1234567891011121314  
```  
  
 다음 코드에서는 `break` 문이 참조는 `for` 앞에 오는 루프는 `Inner:` 문. 때 `j` 가 24는 `break` 문을 사용 하면 프로그램 흐름이 루프를 종료 합니다. 숫자 21부터 23 까지의 각 줄에 인쇄 합니다.  
  
```JavaScript  
Outer:  
for (var i = 1; i <= 10; i++) {  
    document.write ("<br />");  
    document.write ("i: " + i);  
    document.write (" j: ");  
Inner:  
    for (var j = 21; j <= 30; j++) {  
        if (j == 24) {  
            break Inner;  
        }  
        document.write (j + " ");  
    }  
}  
  
// Output:   
// i: 1 j: 21 22 23   
// i: 2 j: 21 22 23   
// i: 3 j: 21 22 23   
// i: 4 j: 21 22 23   
// i: 5 j: 21 22 23   
// i: 6 j: 21 22 23   
// i: 7 j: 21 22 23   
// i: 8 j: 21 22 23   
// i: 9 j: 21 22 23   
// i: 10 j: 21 22 23  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [continue 문](../../javascript/reference/continue-statement-javascript.md)   
 [do...while 문](../../javascript/reference/do-dot-dot-dot-while-statement-javascript.md)   
 [for 문](../../javascript/reference/for-statement-javascript.md)   
 [>for.. 문에서](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [Labeled 문](../../javascript/reference/labeled-statement-javascript.md)   
 [while 문](../../javascript/reference/while-statement-javascript.md)