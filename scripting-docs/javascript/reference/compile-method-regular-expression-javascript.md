---
title: "compile 메서드 (Regular Expression) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: compile
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- regular expressions, compiling
- Compile method
- compiling source code, regular expressions
ms.assetid: dc28cae3-478d-49b5-b5ea-203e5edfe195
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8b8de23a9e4f0e03fbf042195867ad9426e4c6bb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="compile-method-regular-expression-javascript"></a>compile 메서드(Regular Expression)(JavaScript)
정규식을 빠른 실행을 위해 내부 형식으로 컴파일합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
rgExp.compile(pattern, [flags])   
```  
  
## <a name="parameters"></a>매개 변수  
 `rgExp`  
 필수 요소. 인스턴스는 **정규식** 개체입니다. 변수 이름 또는 리터럴일 수 있습니다.  
  
 *패턴*  
 필수 요소. 컴파일할 정규식 패턴을 포함 하는 문자열 식  
  
 `flags`  
 선택 사항입니다. 결합할 수 있는 사용 가능한 플래그는 다음과 같습니다.  
  
-   g (의 모든 항목에 대 한 전역 검색 *패턴*)  
  
-   i(대/소문자 무시)  
  
-   m(여러 줄 검색)  
  
## <a name="remarks"></a>설명  
 **컴파일** 메서드 변환 *패턴* 빠른 실행을 위해 내부 형식으로. 이렇게 하면 보다 효율적으로 활용 루프의 정규식에 대 한 예를 들어 있습니다. 컴파일된 정규식 때 속도가 빨라집니다 같은 식에 반복 해 서 다시 사용 합니다. 그러나 정규식 변경 되 면 아무 이점이 확보 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **컴파일** 메서드:  
  
```JavaScript  
function CompileDemo(){  
   var rs;  
   var s = "AaBbCcDdEeFfGgHhIiJjKkLlMmNnOoPp"  
   // Create regular expression for uppercase only.  
   var r = new RegExp("[A-Z]", "g");  
   var a1 = s.match(r)              // Find matches.  
   // Compile the regular expression for lowercase only.  
   r.compile("[a-z]", "g");  
// Find matches.  
   var a2 = s.match(r)                
   return(a1 + "\n" + a2);  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [정규식 구문 (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)