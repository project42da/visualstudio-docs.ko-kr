---
title: "조건부 컴파일(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ConditionalComp_JavaScript"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "조건부 컴파일"
  - "조건부 컴파일, 개요"
ms.assetid: a843de4e-3aae-43cd-ad64-477dd00814a2
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# 조건부 컴파일(JavaScript)
조건부 컴파일을 사용하면 새로운 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 언어 기능을 지원하지 않는 이전 버전과 호환성을 유지하면서 새 언어 기능을 사용할 수 있습니다.  
  
> [!WARNING]
>  Internet Explorer 11 이전의 모든 Internet Explorer 버전에서는 조건부 컴파일이 지원됩니다.  Internet Explorer 11 표준 모드 이상 및 [!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱에서는 조건부 컴파일이 지원되지 않습니다.  
  
## 문  
 조건부 컴파일은 `@cc_on` 문이나 `@if` 또는 `@set` 문을 사용하여 활성화됩니다.  일반적으로 조건부 컴파일을 사용하면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]의 새로운 기능을 사용하고 스크립트에 디버깅을 지원하며 코드 실행을 추적할 수 있습니다.  
  
 조건부 컴파일 코드는 조건부 컴파일을 지원하지 않는 호스트\(예: Netscape Navigator\)가 이를 무시할 수 있도록 항상 주석에 삽입하십시오.  예를 들면 다음과 같습니다.  
  
```javascript  
/*@cc_on @*/  
/*@if (@_jscript_version >= 4)  
    alert("JavaScript version 4 or better");  
    @else @*/  
    alert("Conditional compilation not supported by this scripting engine.");  
/*@end @*/  
```  
  
 이 예제에서는 `@cc_on` 문에 의해 조건부 컴파일이 활성화된 경우에만 사용되는 특수 주석 구분 기호를 사용합니다.  조건부 컴파일을 지원하지 않는 스크립팅 엔진에는 조건부 컴파일이 지원되지 않는다는 메시지만 표시됩니다.