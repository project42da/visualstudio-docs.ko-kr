---
title: "stackTraceLimit 속성(Error)(JavaScript) | Microsoft Docs"
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
  - "Error.stackTraceLimit"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "오류 스택 추적 제한[JavaScript]"
  - "JavaScript 오류 스택"
  - "오류 스택[JavaScript]"
  - "JavaScript 스택 추적 제한"
ms.assetid: 127ef8e8-892e-4263-9ebc-03364af01212
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# stackTraceLimit 속성(Error)(JavaScript)
표시할 오류 프레임 번호와 일치하는 스택 추적 제한을 가져오거나 설정합니다.  기본 제한은 10입니다.  
  
## 구문  
  
```  
  
Error  
.stackTraceLimit   
```  
  
## 설명  
 `stackTraceLimit` 속성을 0과 `Infinity` 사이 양수 값으로 설정할 수 있습니다.  오류가 throw될 때 `stackTraceLimit` 속성을 0으로 설정하면 스택 추적이 표시되지 않습니다.  속성을 음수 값 또는 숫자가 아닌 값으로 설정하면 값이 0으로 변환됩니다.  stackTraceLimit를 `Infinity`로 설정하면 전체 스택이 표시됩니다.  그렇지 않으면 `ToUint32`가 값을 변환하는 데 사용됩니다.  
  
## 예제  
 다음 예제에서는 스택 추적 제한을 설정하고 가져오는 방법을 보여 줍니다.  
  
```javascript  
try  
    {  
    var err = new Error("my error");  
    Error.stackTraceLimit = 7;  
    throw err;  
    }  
catch(e)  
    {  
    document.write ("Error stack trace limit: ")  
    document.write (Error.stackTraceLimit);  
    }  
```  
  
## 요구 사항  
 Internet Explorer 10 및 [!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱에서 지원됩니다.  
  
 **적용 대상**: [Error 개체](../../javascript/reference/error-object-javascript.md)  
  
## 참고 항목  
 [description 속성\(Error\)](../../javascript/reference/description-property-error-javascript.md)   
 [message 속성\(Error\)](../../javascript/reference/message-property-error-javascript.md)   
 [name 속성\(Error\)](../../javascript/reference/name-property-error-javascript.md)   
 [stack 속성\(Error\)](../../javascript/reference/stack-property-error-javascript.md)