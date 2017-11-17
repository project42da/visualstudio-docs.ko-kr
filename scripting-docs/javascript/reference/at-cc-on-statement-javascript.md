---
title: "@cc_on문 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '@cc_on_JavaScriptKeyword'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- conditional compilation, activating
- '@cc_on statement'
- '@set statement'
- '@if statement'
ms.assetid: fdeda7ee-b9f4-4e52-8aa2-21c90c02a332
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7e993d5bc8302931a5722495da70612e79f7dfd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ccon-statement-javascript"></a>@cc_on문 (JavaScript)
스크립트에서 주석 내의 조건부 컴파일 지원을 활성화합니다.  
  
> [!WARNING]
>  Internet Explorer 11 표준 모드 및 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에서는 조건부 컴파일이 지원되지 않습니다. Internet Explorer 10 표준 모드 및 이전의 모든 버전에서는 조건부 컴파일이 지원됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
@cc_on   
```  
  
## <a name="remarks"></a>설명  
 `@cc_on` 문은 스크립트에서 주석 내의 조건부 컴파일을 활성화합니다.  
  
 ASP나 ASP.NET 페이지 또는 명령줄 프로그램을 위해 작성된 스크립트에서는 다른 메서드를 사용하여 컴파일 기능을 결정할 수 있기 때문에 조건부 컴파일 변수를 사용하는 경우는 많지 않습니다.  
  
 웹 페이지용 스크립트를 작성할 때는 조건부 컴파일 코드를 항상 주석에 포함시킵니다. 이렇게 하면 조건부 컴파일을 지원하지 않는 호스트인 경우 그 부분의 코드를 무시할 수 있습니다.  
  
 조건부 컴파일을 지원하지 않는 브라우저는 스크립트를 유효한 구문으로 허용하므로 `@cc_on` 문을 주석에 사용하는 것이 좋습니다.  
  
 또한 주석 외부에 `@if` 문이나 `@set` 문을 사용해도 조건부 컴파일을 활성화할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제는 `@cc_on` 문의 사용 예를 보여줍니다.  
  
```JavaScript  
/*@cc_on @*/  
/*@  
    document.write("JavaScript version: " + @_jscript_version + ".");  
    document.write("<br />");  
    @if (@_win32)  
        document.write("Running on the 32-bit version of Windows.");  
    @elif (@_win16)  
        document.write("Running on the 16-bit version of Windows.");  
    @else  
        document.write("Running on a different operating system.");  
    @end  
@*/  
```  
  
## <a name="requirements"></a>요구 사항  
 Internet Explorer의 모든 버전에서 지원되지만 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에서는 지원되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [조건부 컴파일](../../javascript/advanced/conditional-compilation-javascript.md)   
 [조건부 컴파일 변수](../../javascript/advanced/conditional-compilation-variables-javascript.md)   
 [@if문](../../javascript/reference/at-if-statement-javascript.md)   
 [@set 문](../../javascript/reference/at-set-statement-javascript.md)