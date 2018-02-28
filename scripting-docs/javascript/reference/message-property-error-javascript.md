---
title: "message 속성 (Error) (JavaScript) | Microsoft Docs"
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
- message
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Message property
ms.assetid: 8cab0392-e0db-4714-827c-47ab04e8b4f2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9dbd2db6c6d31dc48d90c3b07d2388eacf73ae7a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="message-property-error-javascript"></a>message 속성(Error)(JavaScript)
오류 메시지 문자열을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
errorObj.message  
```  
  
## <a name="parameters"></a>매개 변수  
 `errorObj`  
 필수 요소. 인스턴스 `Error` 개체입니다.  
  
## <a name="remarks"></a>설명  
 `message` 속성 특정 오류와 관련 된 오류 메시지를 포함 하는 문자열을 반환 합니다.  
  
 `description` 및 `message` 속성 동일한 기능을 제공 합니다. `description` 속성은 이전 버전과 호환성 제공; `message` 속성 ECMA 표준을 준수 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 TypeError 예외를 throw 하 고 오류 이름과 해당 메시지를 표시 합니다.  
  
```JavaScript  
try  
{  
    // Cause an error.  
    var x = y;  
}  
catch(e)  
{  
    document.write ("Error Message: " + e.message);  
    document.write ("<br />");  
    document.write ("Error Code: ");  
    document.write (e.number & 0xFFFF)  
    document.write ("<br />");  
    document.write ("Error Name: " + e.name);  
}  
```  
  
## <a name="example"></a>예제  
 이 코드의 출력은 다음과 같습니다.  
  
```JavaScript  
Error Message: 'y' is undefined  
Error Code: 5009  
Error Name: TypeError  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
 **적용 대상**: [Error 개체](../../javascript/reference/error-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [description 속성 (Error)](../../javascript/reference/description-property-error-javascript.md)   
 [name 속성(Error)](../../javascript/reference/name-property-error-javascript.md)