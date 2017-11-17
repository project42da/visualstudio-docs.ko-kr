---
title: "continue 문 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: continue_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- do...while statement
- continue statement
- loop structures, continue statement
ms.assetid: f8a30d9f-e2de-4e1f-8668-4e4cf95f7df9
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 391f919c4d06a6c529bfee34e21ca7238b3c63b7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="continue-statement-javascript"></a>continue 문(JavaScript)
루프의 현재 반복을 중지하고 새 반복을 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
continue [label];  
```  
  
## <a name="remarks"></a>설명  
 선택적 `label` 인수를 지정 하면 문이 `continue` 적용 됩니다.  
  
 사용할 수는 `continue` 문 내부에는 `while`, `do...while`, **에 대 한**, 또는 `for...in` 루프입니다. 실행 된 `continue` 문은 루프의 현재 반복을 중지 하 고 루프의 시작 부분을 사용 하 여 프로그램 흐름을 계속 합니다. 이 루프의 서로 다른 형식에 다음과 같은 효과가 있습니다.  
  
-   `while`및 `do...while` 루프 해당 조건을 테스트 하 고 true 인 경우 루프를 다시 실행 합니다.  
  
-   `for`루프는 증가 식을 실행 및 테스트 식이 true 이면 루프를 다시 실행 합니다.  
  
-   `for...in`루프를 다음 필드로 지정 된 변수의 진행 한 루프를 다시 실행 합니다.  
  
## <a name="examples"></a>예제  
 이 예제에서는 1부터 9 까지의 루프를 반복합니다. 사이 있는 문은 `continue` 의 끝과는 `for` 본문의 사용 되기 때문에 생략 됩니다는 `continue` 문 식 함께 `(i < 5)`합니다.  
  
```JavaScript  
for (var i = 1; i < 10; i++) {  
    if (i < 5) {  
        continue;  
    }  
    document.write (i);  
    document.write (" ");  
}  
  
// Output: 5 6 7 8 9  
```  
  
 다음 코드에서는 `continue` 문이 참조는 `for` 앞에 오는 루프는 `Inner:` 레이블. 때 `j` 24는 `continue` 문을 사용 하면는 `for` 루프를 다음 반복으로 이동 합니다. 숫자 21-23과 25 30 사이의 각 줄에 인쇄 합니다.  
  
```JavaScript  
Outer:  
for (var i = 1; i <= 10; i++) {  
    document.write ("<br />");  
    document.write ("i: " + i);  
    document.write (" j: ");  
  
Inner:  
    for (var j = 21; j <= 30; j++) {  
        if (j == 24) {  
             continue Inner;  
        }  
        document.write (j + " ");  
    }  
}  
  
//Output:  
//i: 1 j: 21 22 23 25 26 27 28 29 30   
//i: 2 j: 21 22 23 25 26 27 28 29 30   
//i: 3 j: 21 22 23 25 26 27 28 29 30   
//i: 4 j: 21 22 23 25 26 27 28 29 30   
//i: 5 j: 21 22 23 25 26 27 28 29 30   
//i: 6 j: 21 22 23 25 26 27 28 29 30   
//i: 7 j: 21 22 23 25 26 27 28 29 30   
//i: 8 j: 21 22 23 25 26 27 28 29 30   
//i: 9 j: 21 22 23 25 26 27 28 29 30   
//i: 10 j: 21 22 23 25 26 27 28 29 30  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [break 문](../../javascript/reference/break-statement-javascript.md)   
 [do...while 문](../../javascript/reference/do-dot-dot-dot-while-statement-javascript.md)   
 [for 문](../../javascript/reference/for-statement-javascript.md)   
 [>for.. 문에서](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [Labeled 문](../../javascript/reference/labeled-statement-javascript.md)   
 [while 문](../../javascript/reference/while-statement-javascript.md)