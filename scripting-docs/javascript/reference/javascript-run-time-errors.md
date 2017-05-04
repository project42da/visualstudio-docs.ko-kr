---
title: "JavaScript 런타임 오류 | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT-32725"
  - "VS.WebClient.Help.SCRIPT7002"
  - "VS.WebClient.Help.SCRIPT1001"
  - "VS.WebClient.Help.SCRIPT16389"
  - "VS.WebClient.HelpSCRIPT50"
  - "VS.WebClient.HelpSCRIPT70"
  - "VS.WebClient.HelpSCRIPT87"
  - "VS.WebClient.HelpSCRIPT65535"
  - "VS.WebClient.HelpSCRIPT445"
  - "VS.WebClient.HelpSCRIPT600"
  - "VS.WebClient.HelpSCRIPT2343"
  - "VS.WebClient.HelpSCRIPT122"
  - "VS.WebClient.HelpSCRIPT28"
  - "VS.WebClient.HelpSCRIPT16386"
  - "VS.WebClient.HelpSCRIPT7015"
  - "VS.WebClient.HelpSCRIPT3"
  - "VS.WebClient.HelpSCRIPT16388"
  - "VS.WebClient.HelpSCRIPT14"
  - "VS.WebClient.HelpSCRIPT12030"
  - "VS.WebClient.HelpSCRIPT12029"
  - "VS.WebClient.HelpSCRIPT1001"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "오류[JavaScript]"
  - "런타임 오류, JavaScript"
ms.assetid: c111469d-8f31-4bde-9d46-16d58775db7d
caps.latest.revision: 20
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 20
---
# JavaScript 런타임 오류
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 런타임 오류는 시스템이 실행할 수 없는 작업을 스크립트에서 수행하려고 시도하면 발생하는 오류입니다. 변수 식을 평가하거나 메모리를 할당할 때 런타임 오류가 발생할 수 있습니다.  
  
## Windows 런타임 오류  
 [!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱에서 Windows 런타임 API를 사용하는 경우 Windows 런타임 HRESULT에서 변환된 JavaScript 오류가 표시될 수 있습니다. 0x80070000 범위를 벗어나는 Windows 런타임 HRESULT는 낮은 비트의 16진수 값을 가져온 다음 10진수로 변환하는 방식을 통해 JavaScript 오류로 변환됩니다. 예를 들어 HRESULT 0x80070032는 10진수 값 50으로 변환되므로 여기에 해당하는 JavaScript 오류는 SCRIPT50입니다. HRESULT 0x80074005는 10진수 값 16389로 변환되므로 여기에 해당하는 JavaScript 오류는 SCRIPT16389입니다.  
  
## 오류  
  
|오류 번호|설명|  
|-----------|--------|  
|5|[액세스가 거부되었습니다.](../../javascript/misc/access-is-denied.md)|  
|438|[개체에서 이 속성 또는 메서드를 지원하지 않음](../../javascript/misc/object-doesn-t-support-this-property-or-method.md)|  
|1001|메모리 부족|  
|5029|[배열의 길이는 유한한 양의 정수여야 합니다.](../../javascript/misc/array-length-must-be-a-finite-positive-integer.md)|  
|5030|[배열의 길이는 유한한 양수로 할당해야 합니다.](../../javascript/misc/array-length-must-be-assigned-a-finite-positive-number.md)|  
|5028|[Array 또는 Arguments 개체가 필요합니다.](../../javascript/misc/array-or-arguments-object-expected.md)|  
|5010|[부울이 필요합니다.](../../javascript/misc/boolean-expected.md)|  
|5003|[함수 결과에 할당할 수 없습니다.](../../javascript/misc/cannot-assign-to-a-function-result.md)|  
|5000|['this'에 할당할 수 없습니다.](../../javascript/misc/cannot-assign-to-this.md)|  
|5034|[값 인수에 순환 참조를 사용하는 것은 지원되지 않습니다.](../../javascript/misc/circular-reference-in-value-argument-not-supported.md)|  
|5006|[Date 개체가 필요합니다.](../../javascript/misc/date-object-expected.md)|  
|5015|[Enumerator 개체가 필요합니다.](../../javascript/misc/enumerator-object-expected.md)|  
|5022|[예외가 throw되었지만 catch할 수 없습니다.](../../javascript/misc/exception-thrown-and-not-caught.md)|  
|5020|[정규식에 '\)'가 필요합니다.](../../javascript/misc/expected-right-parenthesis-in-regular-expression-javascript.md)|  
|5019|[정규식에 '&#93;'가 필요합니다.](../../javascript/misc/expected-right-square-bracket-in-regular-expression-javascript.md)|  
|5023|[함수에 유효한 프로토타입 개체가 없습니다.](../../javascript/misc/function-does-not-have-a-valid-prototype-object.md)|  
|5002|[함수가 필요합니다.](../../javascript/misc/function-expected.md)|  
|5008|[잘못된 할당입니다.](../../javascript/misc/illegal-assignment-javascript.md)|  
|5021|[문자 집합에서 범주가 잘못되었습니다.](../../javascript/misc/invalid-range-in-character-set-javascript.md)|  
|5035|[치환 인수가 잘못되었습니다.](../../javascript/misc/invalid-replacer-argument.md)|  
|5014|[JavaScript 개체가 필요합니다.](../../javascript/misc/javascript-object-expected.md)|  
|5001|[숫자가 필요합니다.](../../javascript/misc/number-expected.md)|  
|5007|[개체가 필요합니다.](../../javascript/misc/object-expected.md)|  
|5012|[개체 멤버가 필요합니다.](../../javascript/misc/object-member-expected.md)|  
|5016|[정규식 개체가 필요합니다.](../../javascript/misc/regular-expression-object-expected.md)|  
|5005|[문자열이 필요합니다.](../../javascript/misc/string-expected.md)|  
|5017|[정규식에 구문 오류가 있습니다.](../../javascript/misc/syntax-error-in-regular-expression-javascript.md)|  
|5026|[소수 자리수가 범위를 초과하였습니다.](../../javascript/misc/the-number-of-fractional-digits-is-out-of-range.md)|  
|5027|[정밀도가 범위를 초과하였습니다.](../../javascript/misc/the-precision-is-out-of-range.md)|  
|5025|[디코딩될 URI가 유효한 인코딩이 아닙니다.](../../javascript/misc/the-uri-to-be-decoded-is-not-a-valid-encoding.md)|  
|5024|[인코딩될 URI에 잘못된 문자가 있습니다.](../../javascript/misc/the-uri-to-be-encoded-contains-an-invalid-character.md)|  
|5009|[식별자가 정의되지 않았습니다.](../../javascript/misc/undefined-identifier.md)|  
|5018|[예기치 않은 한정사입니다.](../../javascript/misc/unexpected-quantifier-javascript.md)|  
|5013|[VBArray가 필요합니다.](../../javascript/misc/vbarray-expected.md)|  
  
## 참고 항목  
 [JavaScript 구문 오류](../../javascript/reference/javascript-syntax-errors.md)