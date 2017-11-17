---
title: "for 문 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: for_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: loop structures, for statements
ms.assetid: bae0ec40-152e-43f3-969b-3696489ec5c4
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7142dbb8c00a351918d0821c3ca7dba3d7b2acb6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="for-statement-javascript"></a>for 문(JavaScript)
지정된 된 조건이 true 인에 대 한 문 블록을 실행 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
for ([initialization]; [test]; [increment])  
   statement   
```  
  
## <a name="parameters"></a>매개 변수  
 `initialization`  
 선택 사항입니다. 식입니다. 이 식은 루프를 실행 하기 전에 한 번만 실행 됩니다.  
  
 `test`  
 선택 사항입니다. 부울 식입니다. 경우 `test` 은 `true`, `statement` 실행 됩니다. 경우 `test` 경우 `false`, 루프 종료 됩니다.  
  
 `increment`  
 선택 사항입니다. 식입니다. 증분식 모든 루프의 끝에서 실행 됩니다.  
  
 `statement`  
 선택 사항입니다. 될 경우 실행할 하나 이상의 문을 `test` 은 **true**합니다. 복합 문일 수 있습니다.  
  
## <a name="remarks"></a>설명  
 일반적으로 사용 하는 `for` 를 지정한 수 알려진된 여러 번 실행할 때 루프를 반복 합니다. A `for` 루프는 배열을 반복 하 고 순차적 처리를 수행 하는 데 유용 합니다.  
  
 따라서 루프의 실행 전에 발생 조건식의 테스트는 `for` 문은 0 번 이상 실행 합니다.  
  
 줄는 `for` 사용할 수 있습니다, 루프 문 블록은 `break` 루프를 종료 하는 문을 사용할 수는 `continue` 루프의 다음 반복으로 제어를 전송 하는 문입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `for` 문이 포함된 된 문을 다음과 같이 실행:  
  
-   먼저, 변수의 초기 값 `i` 평가 됩니다.  
  
-   값으로 이상, 다음 `i` 9, 보다 작은 `document.write` 문을 실행 하 고 `i` 식이 다시 계산 됩니다.  
  
-   때 `i` 9 보다 큰 조건이 false가 고 고 루프 바깥쪽 제어가 전달 됩니다.  
  
```JavaScript  
// i is set to 0 at the start and is incremented by 1 at the  
// end of each iteration.  
// The loop terminates when i is not less than or equal to  
// 9 before a loop iteration.  
for (var i = 0; i <= 9; i++) {  
   document.write (i);  
   document.write (" ");  
}  
  
// Output: 0 1 2 3 4 5 6 7 8 9  
```  
  
## <a name="example"></a>예제  
 모든의 식을 고 `for` 문에 선택 사항입니다. 다음 예제에서는 `for` 문은 무한 루프를 생성 및 `break` 문을 사용 하 여 루프를 종료 합니다.  
  
```JavaScript  
var j = 0;  
for (;;) {  
    if (j >= 5) {  
        break;  
    }  
    j++;  
    document.write (j + " ");  
}  
  
// Output: 1 2 3 4 5  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [>for.. 문에서](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [while 문](../../javascript/reference/while-statement-javascript.md)