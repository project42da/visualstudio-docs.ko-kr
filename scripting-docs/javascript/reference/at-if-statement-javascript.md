---
title: "@if 문(JavaScript) | Microsoft Docs"
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
  - "@if_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "@if 문"
  - "조건문, if"
  - "elif 문"
  - "else 문"
  - "if 문, @if"
ms.assetid: ff11b29d-c06a-4276-b11d-db73e2da98ac
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 18
---
# @if 문(JavaScript)
식의 값에 따라 문 그룹을 조건부로 실행합니다.  
  
> [!WARNING]
>  Internet Explorer 11 표준 모드 및 [!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱에서는 조건부 컴파일이 지원되지 않습니다.  Internet Explorer 10 표준 모드 및 이전의 모든 버전에서는 조건부 컴파일이 지원됩니다.  
  
## 구문  
  
```  
  
      @if (  
   condition1  
)  
   text1  
[@elif (  
   condition2  
)  
   text2]  
[@else  
   text3]  
@end   
```  
  
## 매개 변수  
 *condition1, condition2*  
 선택 사항  Boolean 식으로 강제 변환할 수 있는 식입니다.  
  
 `text1`  
 선택 사항  `condition1`이 **true**일 경우 구문 분석되는 텍스트입니다.  
  
 `text2`  
 선택 사항  `condition1`이 **false**이고 `condition2`가 **true**일 경우 구문 분석되는 텍스트입니다.  
  
 `text3`  
 선택 사항  `condition1`과 `condition2`가 모두 **false**일 경우 구문 분석되는 텍스트입니다.  
  
## 설명  
 `@if` 문을 쓸 때 각 절을 다른 줄에 둘 필요는 없습니다.  여러 개의 **@elif** 절을 사용할 수 있습니다.  그러나 모든 **@elif** 절은 **@else** 절 앞에 와야 합니다.  
  
 일반적으로 `@if` 문을 사용하여 여러 옵션 중 어떤 텍스트를 텍스트 출력에 사용할지 결정합니다.  
  
 ASP나 ASP.NET 페이지 또는 명령줄 프로그램을 위해 작성된 스크립트에서는 다른 메서드를 사용하여  컴파일러 기능을 결정할 수 있기 때문에 조건부 컴파일 변수를 사용하는 경우는 많지 않습니다.  
  
 웹 페이지용 스크립트를 작성할 때는 조건부 컴파일 코드를 항상 주석에 추가합니다.  이렇게 하면 조건부 컴파일을 지원하지 않는 호스트인 경우 그 부분의 코드를 무시할 수 있습니다.  
  
## 예제  
 다음 예제에서는 **@if...@elif…@else...@end** 문의 사용법을 보여줍니다.  
  
```javascript  
/*@cc_on @*/  
/*@  
    document.write("JavaScript version: " + @_jscript_version + ".");  
    document.write("<br />");  
    @if (@_win32)  
        document.write("Running on a 32-bit version of Windows.");  
    @elif (@_win16)  
        document.write("Running on a 16-bit version of Windows.");  
    @else  
        document.write("Running on a different operating system.");  
    @end  
@*/  
```  
  
## 요구 사항  
 Internet Explorer의 모든 버전에서 지원되지만 [!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱에서는 지원되지 않습니다.  
  
## 참고 항목  
 [조건부 컴파일](../../javascript/advanced/conditional-compilation-javascript.md)   
 [조건부 컴파일 변수](../../javascript/advanced/conditional-compilation-variables-javascript.md)   
 [@cc\_on 문](../../javascript/reference/at-cc-on-statement-javascript.md)   
 [@set 문](../../javascript/reference/at-set-statement-javascript.md)