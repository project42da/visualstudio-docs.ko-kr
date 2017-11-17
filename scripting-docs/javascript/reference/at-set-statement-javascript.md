---
title: "@set문 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '@set_JavaScriptKeyword'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '@set statement'
- conditional compilation, variables
ms.assetid: 36f15926-3e69-422d-82a2-d186dc088203
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 10f74a1d57a61d78897b660812a6fd8078244b6b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="set-statement-javascript"></a>@set문 (JavaScript)
조건부 컴파일 문에 사용되는 변수들을 만듭니다.  
  
> [!WARNING]
>  Internet Explorer 11 표준 모드 및 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에서는 조건부 컴파일이 지원되지 않습니다. Internet Explorer 10 표준 모드 및 이전의 모든 버전에서는 조건부 컴파일이 지원됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
@set @varname = term   
```  
  
## <a name="parameters"></a>매개 변수  
 *varname*  
 필수 요소. 올바른 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 변수 이름입니다. 항상 앞에 "@" 문자가 나와야 합니다.  
  
 `term`  
 필수 요소. 0개 이상의 단일 연산자이며 상수, 조건부 컴파일 변수 또는 괄호로 묶인 식이 뒤에 나옵니다.  
  
## <a name="remarks"></a>설명  
 조건부 컴파일에는 Number 및 Boolean 변수가 지원되며 Strings 변수는 지원되지 않습니다. `@set`으로 만든 변수는 보통 조건부 컴파일 문에서 사용하지만 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 코드 어디에서나 사용할 수 있습니다.  
  
 변수 선언 예제는 다음과 같습니다.  
  
```JavaScript  
  
      @set @myvar1 = 12  
  
@set @myvar2 = (@myvar1 * 20)  
  
@set @myvar3 = @_jscript_version  
```  
  
 다음 연산자는 괄호로 묶인 식에서 사용할 수 있습니다.  
  
-   `! ~`  
  
-   `* / %`  
  
-   `+ -`  
  
-   `<< >> >>>`  
  
-   `< <= > >=`  
  
-   `== != === !==`  
  
-   `& ^ |`  
  
-   `&& | |`  
  
 변수를 정의하기 전에 사용하는 경우 해당 변수의 값은 `NaN`입니다. `NaN` 문을 사용하여 `@if` 여부를 확인할 수 있습니다.  
  
```JavaScript  
@if (@newVar != @newVar)  
   ...  
```  
  
 `NaN`은 자기 자신과 같지 않은 유일한 값이므로 이 방법을 사용합니다.  
  
## <a name="requirements"></a>요구 사항  
 Internet Explorer의 모든 버전에서 지원되지만 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에서는 지원되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [조건부 컴파일](../../javascript/advanced/conditional-compilation-javascript.md)   
 [조건부 컴파일 변수](../../javascript/advanced/conditional-compilation-variables-javascript.md)   
 [@cc_on문](../../javascript/reference/at-cc-on-statement-javascript.md)   
 [@if 문](../../javascript/reference/at-if-statement-javascript.md)