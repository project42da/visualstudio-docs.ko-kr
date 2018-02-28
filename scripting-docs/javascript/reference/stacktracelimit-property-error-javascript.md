---
title: "stackTraceLimit 속성 (Error) (JavaScript) | Microsoft Docs"
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
- Error.stackTraceLimit
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- error stack track limit [JavaScript]
- JavaScript error stack
- error stack [JavaScript]
- JavaScript stack trace limit
ms.assetid: 127ef8e8-892e-4263-9ebc-03364af01212
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9af736ee8b385f93b761f1dfa021c23ee5376292
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="stacktracelimit-property-error-javascript"></a>stackTraceLimit 속성(Error)(JavaScript)
표시할 오류 프레임 수에 해당 하는 스택 추적 제한을 가져오거나 설정 합니다. 기본 제한은 10입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Error  
.stackTraceLimit   
```  
  
## <a name="remarks"></a>설명  
 설정할 수 있습니다는 `stackTraceLimit` 속성을 0 사이의 양수 값 및 `Infinity`합니다. 경우는 `stackTraceLimit` 속성이 설정 되어 스택 추적이 없습니다 오류가 발생 한 시간에 0으로 표시 됩니다. 음수 값 또는 숫자가 아닌 값으로 속성은 값을 0으로 변환 됩니다. stackTraceLimit로 설정 되어 있으면 `Infinity`, 전체 스택에 표시 됩니다. 그렇지 않으면 `ToUint32` 값으로 변환 하는 데 사용 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에는 설정 하 고 다음 스택 추적 제한을 가져오는 방법을 보여 줍니다.  
  
```JavaScript  
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
  
## <a name="requirements"></a>요구 사항  
 및에서 Internet Explorer 10에서에서 지원 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱.  
  
 **적용 대상**: [Error 개체](../../javascript/reference/error-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [description 속성 (Error)](../../javascript/reference/description-property-error-javascript.md)   
 [message 속성 (Error)](../../javascript/reference/message-property-error-javascript.md)   
 [name 속성 (Error)](../../javascript/reference/name-property-error-javascript.md)   
 [stack 속성(Error)](../../javascript/reference/stack-property-error-javascript.md)