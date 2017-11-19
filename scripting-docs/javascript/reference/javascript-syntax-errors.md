---
title: "JavaScript 구문 오류 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: JavaScript
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- errors [JavaScript]
- syntax errors, JavaScript
ms.assetid: 0343dc19-5f5e-4a4c-83da-630b4fbcb3b6
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3bc3398d6a90ef308fd2b4b367bc1006ad95f5b1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="javascript-syntax-errors"></a>JavaScript 구문 오류
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]구문 오류 발생 때 구조 중 하나를 프로그램 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 문 구문 규칙 중 하나 이상 위반 합니다.  
  
## <a name="errors"></a>오류  
  
|오류 번호|설명|  
|------------------|-----------------|  
|1019|[루프 외부에서 'break'를 사용할 수 없음](../../javascript/misc/can-t-have-break-outside-of-loop.md)|  
|1020|[루프 외부에서 'continue'를 사용할 수 없음](../../javascript/misc/can-t-have-continue-outside-of-loop.md)|  
|1030|[조건부 컴파일이 해제됨](../../javascript/misc/conditional-compilation-is-turned-off.md)|  
|1027|['default'는 'switch' 문에 한 번만 사용할 수 있음](../../javascript/misc/default-can-only-appear-once-in-a-switch-statement.md)|  
|1005|[예상 ' ('](../../javascript/misc/expected-left-parenthesis-javascript.md)|  
|1006|[예상 ')'](../../javascript/misc/expected-right-parenthesis-javascript.md)|  
|1012|[필요 합니다. '/'](../../javascript/misc/expected-minus.md)|  
|1003|[':' 필요](../../javascript/misc/expected-colon.md)|  
|1004|[';' 필요](../../javascript/misc/expected-semicolon.md)|  
|1032|['@' 필요](../../javascript/misc/expected-at.md)|  
|1029|['@end' 필요](../../javascript/misc/expected-at-end.md)|  
|1007|[필요 합니다. ' &#93;'](../../javascript/misc/expected-right-square-bracket.md)|  
|1008|['{' 필요](../../javascript/misc/expected-left-curly-brace.md)|  
|1009|['}' 필요](../../javascript/misc/expected-right-curly-brace.md)|  
|1011|['=' 필요합니다.](../../javascript/misc/expected-equal-javascript.md)|  
|1033|['catch' 필요](../../javascript/misc/expected-catch.md)|  
|1031|[상수 필요](../../javascript/misc/expected-constant.md)|  
|1023|[16진수 필요](../../javascript/misc/expected-hexadecimal-digit.md)|  
|1010|[식별자가 있어야 하는데](../../javascript/misc/expected-identifier-javascript.md)|  
|1028|[식별자, 문자열 또는 숫자 필요](../../javascript/misc/expected-identifier-string-or-number.md)|  
|1024|['while' 필요](../../javascript/misc/expected-while.md)|  
|1014|[잘못 된 문자](../../javascript/misc/invalid-character-javascript.md)|  
|1026|[레이블을 찾을 수 없음](../../javascript/misc/label-not-found.md)|  
|1025|[레이블이 다시 정의됨](../../javascript/misc/label-redefined.md)|  
|1018|[함수 외부에 'return' 문이 있음](../../javascript/misc/return-statement-outside-of-function.md)|  
|1002|[구문 오류가 있습니다.](../../javascript/misc/syntax-error-javascript.md)|  
|1035|[같은 소스 줄에서 throw 뒤에는 식이 와야 함](../../javascript/misc/throw-must-be-followed-by-an-expression-on-the-same-source-line.md)|  
|1016|[종결되지 않은 주석](../../javascript/misc/unterminated-comment.md)|  
|1015|[종결 되지 않은 문자열 상수](../../javascript/misc/unterminated-string-constant-javascript.md)|  
  
### <a name="script-host-errors"></a>스크립트 호스트 오류  
 다음과 같은 오류가 오류를 스크립트 호스트를 말하고 제대로 하지만 경우에 따라 표시 될 수 있습니다.  
  
|오류|HRESULT|설명|  
|-----------|-------------|-----------------|  
|SCRIPT_E_RECORDED|0x86664004|스크립트 엔진와 호스트 간에 전달 될 수 오류가 기록 되었습니다. 호스트 오류 코드는 호출자에 게 전달 해야 합니다.|  
|SCRIPT_E_REPORTED|0x80020101|스크립트 엔진 IActiveScriptSite::OnScriptError 통해 호스트에 처리 되지 않은 예외를 보고 했습니다. 호스트는이 오류를 무시 해도 됩니다.|  
|SCRIPT_E_PROPAGATE|0x8002010|다른 스레드에서 될 수 있는 호출자에 게 스크립트 오류를 전파 하는 중입니다. 호스트는 오류 코드는 호출자에 게 전달 해야 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [JavaScript 런타임 오류](../../javascript/reference/javascript-run-time-errors.md)