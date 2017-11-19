---
title: "Debug 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: debug
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Debug object
- Debug object, about Debug object
ms.assetid: 42a367ec-beb1-4e59-8342-34c326eca042
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6286e5db853daa97e43f36a1467abe90cbced5c8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="debug-object-javascript"></a>Debug 개체(JavaScript)
디버거로 출력을 보내는 내장 전역 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
Debug.function  
```  
  
## <a name="remarks"></a>설명  
 Debug 개체를 인스턴스화하지 않습니다. `function`을 호출하여 모든 속성 및 메서드에 액세스할 수 있습니다.  
  
 Internet Explorer 및 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱을 디버그하는 방법에는 여러 가지가 있습니다. [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱의 경우 `write` 개체의 `writeln` 및 `Debug` 함수는 런타임에 Visual Studio **출력** 창에 문자열을 표시합니다. 디버깅에 대 한 자세한 내용은 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱 참조 [디버그 Windows 유니버설 앱 Visual Studio에서](/visualstudio/debugger/debugging-windows-store-and-windows-universal-apps.md)합니다.  
  
 Internet Explorer 스크립트를 디버그하려면 스크립트 디버거가 설치되어 있어야 하며 디버그 모드에서 스크립트를 실행해야 합니다. Internet Explorer 8 이상 버전에는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 디버거가 포함되어 있습니다. 이전 버전의 Internet Explorer를 사용하는 경우 [방법: Internet Explorer에서 스크립트 디버깅 사용 및 시작](http://go.microsoft.com/fwlink/?LinkId=133801)을 참조하세요.  
  
 스크립트를 디버그하지 않는 경우에는 함수가 적용되지 않습니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `write` 함수를 사용하여 변수의 값을 표시합니다.  
  
```JavaScript  
var counter = 42;  
Debug.write("The value of counter is " + counter);  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="constants"></a>상수  
 [Debug 상수](../../javascript/reference/debug-constants.md)  
  
## <a name="properties"></a>속성  
 [Debug.debuggerEnabled 속성](../../javascript/reference/debug-debuggerenabled-property.md) &#124; [Debug.setNonUserCodeExceptions 속성](../../javascript/reference/debug-setnonusercodeexceptions-property.md)  
  
## <a name="functions"></a>함수  
 [Debug.msTraceAsyncCallbackStarting 함수](../../javascript/reference/debug-mstraceasynccallbackstarting-function.md) &#124; [Debug.msTraceAsyncCallbackCompleted 함수](../../javascript/reference/debug-mstraceasynccallbackcompleted-function.md) &#124; [Debug.msTraceAsyncOperationCompleted 함수](../../javascript/reference/debug-mstraceasyncoperationcompleted-function.md) &#124; [Debug.msTraceAsyncOperationStarting 함수](../../javascript/reference/debug-mstraceasyncoperationstarting-function.md) &#124; [Debug.msUpdateAsyncCallbackRelation 함수](../../javascript/reference/debug-msupdateasynccallbackrelation-function.md) &#124; [Debug.write 함수](../../javascript/reference/debug-write-function-javascript.md) &#124; [Debug.writeln 함수](../../javascript/reference/debug-writeln-function-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [debugger 문](../../javascript/reference/debugger-statement-javascript.md)