---
title: "try … catch 마지막 문 (JavaScript)... | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- try_JavaScriptKeyword
- finally_JavaScriptKeyword
- catch_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- try-catch exception handling, finally block
- try-catch exception handling, about try-catch exception handling
- try-catch exception handling, catch block
- try-catch exception handling
ms.assetid: b7a0a54e-dfaa-4e41-bf25-bcaa43e601fb
caps.latest.revision: "28"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b05f15e593aeb7cb921f6237fad30b589cfdfe66
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="trycatchfinally-statement-javascript"></a>try...catch...finally 문(JavaScript)
한 블록에서 throw된 오류가 다른 블록에서 처리되는 코드 블록을 설정합니다. `try` 블록 내부에서 throw된 오류는 `catch` 블록에서 발생합니다. [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)].  
  
## <a name="syntax"></a>구문  
  
```  
try {  
    tryStatements  
}  
catch(exception){  
    catchStatements  
}  
finally {  
    finallyStatements  
}  
```  
  
## <a name="parameters"></a>매개 변수  
 `tryStatements`  
 필수 요소. 오류가 발생할 수 있는 문입니다.  
  
 `exception`  
 필수 요소. 임의의 변수 이름입니다. `exception`의 초기 값은 throw된 오류 값입니다.  
  
 `catchStatements`  
 선택 사항입니다. 연결된 `tryStatements`에서 발생하는 오류를 처리하는 문입니다.  
  
 `finallyStatements`  
 선택 사항입니다. 다른 모든 오류가 처리된 후 무조건 실행되는 문입니다.  
  
## <a name="remarks"></a>설명  
 `try...catch...finally` 문을 사용하면 코드를 실행하면서도 코드 블록에서 발생할 수 있는 오류의 전부를 처리할 수 있습니다. 처리되지 않는 오류가 발생하면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]는 일반 오류 메시지를 제공합니다.  
  
 `try` 블록은 오류를 호출할 수 있는 코드를 포함하지만 `catch` 블록은 일부 또는 모든 오류를 처리하는 코드를 포함합니다. `try` 블록에서 오류가 발생하면 프로그램 제어는 `catch` 블록으로 전달됩니다. `exception` 값은 `try` 블록에서 발생한 오류 값입니다. 오류가 발생하지 않으면 `catch` 블록의 코드는 실행되지 않습니다.  
  
 `throw` 문을 사용하여 오류를 다음 수준으로 전달하여 오류를 다시 throw할 수 있습니다.  
  
 `try` 블록의 모든 문이 실행되고 `catch` 블록에서 오류 처리가 완료되면 오류 처리 여부와 상관없이 `finally` 블록의 문이 실행됩니다. 코드는 `finally` 블록 처리 되지 않은 오류가 발생 하지 않는 한 실행이 보장 (예: 내부 런타임 오류는 **catch** 블록).  
  
## <a name="example"></a>예제  
 다음 예제에서는 `ReferenceError` 예외를 throw하고 오류 이름과 해당 메시지를 표시합니다.  
  
```JavaScript  
try {  
    addalert("bad call");  
}  
catch(e) {  
    document.write ("Error Message: " + e.message);  
    document.write ("<br />");  
    document.write ("Error Code: ");  
    document.write (e.number & 0xFFFF);  
    document.write ("<br />");  
    document.write ("Error Name: " + e.name);  
}  
  
// Output:  
Error Message: 'addalert' is undefined  
Error Code: 5009  
Error Name: ReferenceError  
  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 오류와 중첩된 `try...catch` 블록의 실행을 다시 throw하는 방법을 보여줍니다. 중첩된 `try` 블록에서 오류가 throw되면 중첩된 `catch` 블록에 전달되고 다시 throw됩니다. 중첩된 `finally` 블록은 외부 `catch` 블록이 오류를 처리하기 전에 실행되고 종료될 때 외부 `finally` 블록이 실행됩니다.  
  
```JavaScript  
try {  
    document.write("Outer try running...<br/>");  
  
    try {  
        document.write("Nested try running...<br/>");  
        throw new Error(301, "an error");  
    }  
    catch (e) {  
        document.write ("Nested catch caught " + e.message + "<br/>");  
        throw e;  
    }  
    finally {  
        document.write ("Nested finally is running...<br/>");  
    }  
}  
catch (e) {  
    document.write ("Outer catch caught " + e.message + "<br/>");  
}  
finally {  
    document.write ("Outer finally running");  
}  
  
// Output:  
// Outer try running...  
// Nested try running...  
// Nested catch caught error from nested try  
// Nested finally is running...  
// Outer catch caught error from nested try  
// Outer finally running  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
> [!NOTE]
>  Internet Explorer 8 표준 모드부터는 **catch** 블록은 더 이상 필요 `finally` 실행 되도록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [throw 문](../../javascript/reference/throw-statement-javascript.md)   
 [스크립트 Junkie 구성 마법사 샘플 앱](http://code.msdn.microsoft.com/Script-Junkie-Configuration-543ece24)