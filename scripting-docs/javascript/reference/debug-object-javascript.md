---
title: "Debug 개체(JavaScript) | Microsoft Docs"
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
  - "debug"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Debug 개체"
  - "Debug 개체, Debug 개체 정보"
ms.assetid: 42a367ec-beb1-4e59-8342-34c326eca042
caps.latest.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 19
---
# Debug 개체(JavaScript)
디버거로 출력을 보내는 내장 전역 개체입니다.  
  
## 구문  
  
```  
Debug.function  
```  
  
## 설명  
 Debug 개체를 인스턴스화하지 않습니다.`function`을 호출하여 모든 속성 및 메서드에 액세스할 수 있습니다.  
  
 Internet Explorer 및 [!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱을 디버그하는 방법에는 여러 가지가 있습니다.[!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱의 경우 `Debug` 개체의 `write` 및 `writeln` 함수는 런타임에 Visual Studio **출력** 창에 문자열을 표시합니다.[!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱 디버그에 대한 자세한 내용은 [Visual Studio에서 앱 디버깅](../Topic/Debug%20Store%20apps%20in%20Visual%20Studio.md)를 참조하세요.  
  
 Internet Explorer 스크립트를 디버그하려면 스크립트 디버거가 설치되어 있어야 하며 디버그 모드에서 스크립트를 실행해야 합니다. Internet Explorer 8 이상 버전에는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 디버거가 포함되어 있습니다. 이전 버전의 Internet Explorer를 사용하는 경우 [방법: Internet Explorer에서 스크립트 디버깅 사용 및 시작](http://go.microsoft.com/fwlink/?LinkId=133801)을 참조하세요.  
  
 스크립트를 디버그하지 않는 경우에는 함수가 적용되지 않습니다.  
  
## 예제  
 이 예제에서는 `write` 함수를 사용하여 변수의 값을 표시합니다.  
  
```javascript  
var counter = 42; Debug.write("The value of counter is " + counter);  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## 상수  
 [Debug 상수](../../javascript/reference/debug-constants.md)  
  
## 속성  
 [Debug.debuggerEnabled 속성](../../javascript/reference/debug-debuggerenabled-property.md) &#124; [Debug.setNonUserCodeExceptions 속성](../../javascript/reference/debug-setnonusercodeexceptions-property.md)  
  
## 함수  
 [Debug.msTraceAsyncCallbackStarting 함수](../../javascript/reference/debug-mstraceasynccallbackstarting-function.md) &#124; [Debug.msTraceAsyncCallbackCompleted 함수](../../javascript/reference/debug-mstraceasynccallbackcompleted-function.md) &#124; [Debug.msTraceAsyncOperationCompleted 함수](../../javascript/reference/debug-mstraceasyncoperationcompleted-function.md) &#124; [Debug.msTraceAsyncOperationStarting 함수](../../javascript/reference/debug-mstraceasyncoperationstarting-function.md) &#124; [Debug.msUpdateAsyncCallbackRelation 함수](../../javascript/reference/debug-msupdateasynccallbackrelation-function.md) &#124; [Debug.write 함수](../../javascript/reference/debug-write-function-javascript.md) &#124; [Debug.writeln 함수](../../javascript/reference/debug-writeln-function-javascript.md)  
  
## 참고 항목  
 [debugger 문](../../javascript/reference/debugger-statement-javascript.md)