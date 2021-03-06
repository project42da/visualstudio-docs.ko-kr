---
title: "stack 속성 (Error) (JavaScript) | Microsoft Docs"
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
- Error.stack
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- JavaScript error stack
- error stack [JavaScript]
ms.assetid: 1dc21fdd-853c-4664-bf1c-24eb1f6f2daf
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 14e4a2537b1543b7e8d9727afdeb8ea5dee61bbc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="stack-property-error-javascript"></a>stack 속성(Error)(JavaScript)
오류 스택을 스택 추적 프레임이 포함된 문자열로 가져오거나 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object  
.stack   
```  
  
## <a name="remarks"></a>설명  
 오류가 생성될 때 `stack` 속성이 `undefined`로 설정되고, 오류가 발생할 때 추적 정보를 가져옵니다. 오류가 여러 번 발생하는 경우에는 오류가 발생할 때마다 `stack` 속성이 업데이트됩니다.  
  
 스택 프레임은 다음 형식으로 표시 됩니다: **at FunctionName (\<정규화 된 이름/U >:\<줄 번호 >:\<열 번호 >)**  
  
 고유한 Error 개체를 만들고 스택 추적을 값으로 설정하는 경우에는 오류가 발생할 때 이 값이 덮어써지지 않습니다.  
  
 `stack` 속성은 해당 프레임의 인라인 함수를 표시하지 않습니다. 실제 스택만 표시합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 오류를 catch하는 경우 스택을 가져오는 방법을 보여 줍니다.  
  
```JavaScript  
try  
    {  
        var x = y.name;  
    }  
catch(e)  
    {  
        document.write ("Error stack: ")  
        document.write (e.stack);  
    }  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 스택을 설정한 다음 가져오는 방법을 보여 줍니다.  
  
```JavaScript  
try  
    {  
        var err = Error("my error");  
        err.stack = "my stack trace";  
        throw err;  
    }  
catch(e)  
    {  
        document.write ("Error stack: ")  
        document.write (e.stack);  
    }  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]  
  
 **적용 대상**: [Error 개체](../../javascript/reference/error-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [description 속성 (Error)](../../javascript/reference/description-property-error-javascript.md)   
 [message 속성 (Error)](../../javascript/reference/message-property-error-javascript.md)   
 [name 속성 (Error)](../../javascript/reference/name-property-error-javascript.md)   
 [stackTraceLimit 속성(Error)](../../javascript/reference/stacktracelimit-property-error-javascript.md)