---
title: "eval 함수 (JavaScript) | Microsoft Docs"
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
- eval
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- eval function
- parsing, code
- parser
ms.assetid: 85587e39-9325-4b75-b9f9-9d7d475a2120
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 388e486f58bb70fd192701060a5faefaed8bd98e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="eval-function-javascript"></a>eval 함수(JavaScript)
평가 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 코드 실행 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
eval(codeString)   
```  
  
## <a name="parameters"></a>매개 변수  
 `codeString`  
 필수 요소. A `String` 유효한 포함 된 값 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 코드입니다.  
  
## <a name="remarks"></a>설명  
 `eval` 를 동적으로 실행할 함수를 사용 하면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 소스 코드입니다.  
  
 `codeString` 하 여 문자열 구문 분석 되는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 파서가 실행 합니다.  
  
 에 전달 된 코드는 `eval` 함수에 대 한 호출으로 동일한 컨텍스트에서 실행 되는 `eval` 함수입니다.  
  
 사용 가능한 경우 항상는 [JSON.parse 함수](../../javascript/reference/json-parse-function-javascript.md) 개체 JSON (JavaScript Notation) 텍스트를 역직렬화 할 합니다. `JSON.parse` 함수는 더 안전 하 고 더 빠르게 실행 보다는 `eval` 함수입니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 변수 초기화 `myDate` 테스트 날짜입니다.  
  
```JavaScript  
var dateFn = "Date(1971,3,8)";  
var myDate;  
eval("myDate = new " + dateFn + ";");  
  
document.write(myDate);  
  
// Output: Thu Apr 8 00:00:00 PDT 1971  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [전역 개체](../../javascript/reference/global-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [String 개체](../../javascript/reference/string-object-javascript.md)