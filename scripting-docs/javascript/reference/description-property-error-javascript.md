---
title: "description 속성 (Error) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Description
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- error handling, error description
- Description property
- errors, description
ms.assetid: ea727f1e-2041-4400-965c-67e6d47a1ff0
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6135951fdf65698ed48b9bbacdcc55c1aac22d41
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="description-property-error-javascript"></a>description 속성(Error)(JavaScript)
반환 하거나 특정 오류와 관련 된 설명 문자열을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object  
.description [= stringExpression]  
```  
  
## <a name="parameters"></a>매개 변수  
 *object*  
 필수 요소. 모든 인스턴스는 `Error` 개체입니다.  
  
 `stringExpression`  
 선택 사항입니다. 오류에 대 한 설명을 포함 하는 문자열 식입니다.  
  
## <a name="remarks"></a>설명  
 **설명** 속성 특정 오류와 관련 된 오류 메시지 문자열을 포함 합니다. 오류에는 사용자에 게 알리도록 하려면이 속성에 포함 된 값을 사용 합니다.  
  
 **설명** 및 **메시지** 같은 기능을 제공 하는 속성, **설명** 속성은 이전 버전과 호환성 제공;  **메시지** 속성 ECMA 표준을 준수 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **설명** 속성입니다.  
  
```JavaScript  
try  
{  
// Cause an error:  
    x = y     
}  
catch(e)  
{  
// Prints "[object Error]":  
    document.write(e)  
    document.write (" ");  
// Prints 5009:  
    document.write((e.number & 0xFFFF))    
    document.write (" ");  
// Prints "'y' is undefined":  
    document.write(e.description);  
    document.write (" ");  
// Prints "'y' is undefined":  
    document.write(e.message)  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
 **적용 대상**: [Error 개체](../../javascript/reference/error-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [number 속성 (Error)](../../javascript/reference/number-property-error-javascript.md)   
 [message 속성 (Error)](../../javascript/reference/message-property-error-javascript.md)   
 [name 속성(Error)](../../javascript/reference/name-property-error-javascript.md)