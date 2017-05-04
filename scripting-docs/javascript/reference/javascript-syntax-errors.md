---
title: "JavaScript 구문 오류 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "JavaScript"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "오류[JavaScript]"
  - "구문 오류, JavaScript"
ms.assetid: 0343dc19-5f5e-4a4c-83da-630b4fbcb3b6
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# JavaScript 구문 오류
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 문의 구조가 구문 규칙을 하나 이상 위반하면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 구문 오류가 발생합니다.  
  
## 오류  
  
|오류 번호|설명|  
|-----------|--------|  
|1019|[루프 외부에 'break'를 사용할 수 없습니다.](../../javascript/misc/can-t-have-break-outside-of-loop.md)|  
|1020|[루프 외부에 ''continue'를 사용할 수 없습니다.](../../javascript/misc/can-t-have-continue-outside-of-loop.md)|  
|1030|[조건부 컴파일이 해제되었습니다.](../../javascript/misc/conditional-compilation-is-turned-off.md)|  
|1027|['default'는 'switch' 문에서 한 번만 사용할 수 있습니다.](../../javascript/misc/default-can-only-appear-once-in-a-switch-statement.md)|  
|1005|['\('가 필요합니다.](../../javascript/misc/expected-left-parenthesis-javascript.md)|  
|1006|['\)'가 필요합니다.](../../javascript/misc/expected-right-parenthesis-javascript.md)|  
|1012|['\/'가 필요합니다.](../../javascript/misc/expected-minus.md)|  
|1003|[':'가 필요합니다.](../../javascript/misc/expected-colon.md)|  
|1004|[';'가 필요합니다.](../../javascript/misc/expected-semicolon.md)|  
|1032|['@'가 필요합니다.](../../javascript/misc/expected-at.md)|  
|1029|['@end'가 필요합니다.](../../javascript/misc/expected-at-end.md)|  
|1007|['&#93;'가 필요합니다.](../../javascript/misc/expected-right-square-bracket.md)|  
|1008|['{'가 필요합니다.](../../javascript/misc/expected-left-curly-brace.md)|  
|1009|['}'가 필요합니다.](../../javascript/misc/expected-right-curly-brace.md)|  
|1011|['\='가 필요합니다.](../../javascript/misc/expected-equal-javascript.md)|  
|1033|['catch'가 필요합니다.](../../javascript/misc/expected-catch.md)|  
|1031|[상수가 필요합니다.](../../javascript/misc/expected-constant.md)|  
|1023|[16진수가 필요합니다.](../../javascript/misc/expected-hexadecimal-digit.md)|  
|1010|[식별자가 필요합니다.](../../javascript/misc/expected-identifier-javascript.md)|  
|1028|[식별자, 문자열 또는 숫자가 필요합니다.](../../javascript/misc/expected-identifier-string-or-number.md)|  
|1024|['while'이 필요합니다.](../../javascript/misc/expected-while.md)|  
|1014|[잘못된 문자입니다.](../../javascript/misc/invalid-character-javascript.md)|  
|1026|[레이블을 찾을 수 없습니다.](../../javascript/misc/label-not-found.md)|  
|1025|[레이블이 다시 정의되었습니다.](../../javascript/misc/label-redefined.md)|  
|1018|[함수 외부에 'return' 문이 있습니다.](../../javascript/misc/return-statement-outside-of-function.md)|  
|1002|[구문 오류입니다.](../../javascript/misc/syntax-error-javascript.md)|  
|1035|[같은 소스 줄에서 Throw 뒤에는 식이 와야 합니다.](../../javascript/misc/throw-must-be-followed-by-an-expression-on-the-same-source-line.md)|  
|1016|[종결되지 않은 주석입니다.](../../javascript/misc/unterminated-comment.md)|  
|1015|[종결되지 않은 문자열 상수입니다.](../../javascript/misc/unterminated-string-constant-javascript.md)|  
  
### 스크립트 호스트 오류  
 다음 오류는 스크립트 호스트에 대한 정확한 오류이지만 자주 발생하지는 않습니다.  
  
|오류|HRESULT|설명|  
|--------|-------------|--------|  
|SCRIPT\_E\_RECORDED|0x86664004|스크립트 엔진 및 호스트 간에 전달되도록 오류가 기록되었습니다.  호스트는 오류 코드를 호출자에게 전달해야 합니다.|  
|SCRIPT\_E\_REPORTED|0x80020101|스크립트 엔진에서 IActiveScriptSite::OnScriptError를 통해 호스트로 처리되지 않은 예외를 보고했습니다.  호스트에서 이 오류를 무시할 수 있습니다.|  
|SCRIPT\_E\_PROPAGATE|0x8002010|스크립트 오류가 다른 스레드에 있을 수 있는 호출자에게 전파되고 있습니다.  호스트는 오류 코드를 호출자에게 전달해야 합니다.|  
  
## 참고 항목  
 [JavaScript 런타임 오류](../../javascript/reference/javascript-run-time-errors.md)