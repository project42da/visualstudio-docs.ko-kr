---
title: "number 속성 (Error) (JavaScript) | Microsoft Docs"
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
- Number
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Number property
ms.assetid: 8697e20b-a2b0-4e26-85c0-ab07ddfe8281
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bbc229e7d0572e1a3dbed056b344da7ff9ce7292
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="number-property-error-javascript"></a>number 속성(Error)(JavaScript)
반환 하거나 특정 오류와 관련 된 숫자 값을 설정 합니다. `Error` 개체의 기본 속성은 **번호**합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object  
.number [= errorNumber]  
```  
  
## <a name="parameters"></a>매개 변수  
 *개체*  
 모든 인스턴스는 `Error` 개체입니다.  
  
 *errorNumber*  
 오류를 나타내는 정수입니다.  
  
## <a name="remarks"></a>설명  
 오류 번호는 32비트 값입니다. 상위 16 비트 단어는 장치 코드 및 하위 워드 오류 코드입니다. 오류 코드를 확인 하려면 사용 하 여는 `&` (비트 및) 연산자를 16 진수 숫자와 숫자 속성을 결합 `0xFFFF`합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 예외를 throw 하 고 오류 번호에서 파생 된 오류 코드를 표시 합니다.  
  
```JavaScript  
try  
    {  
    // Cause an error.  
    var x = y;  
    }  
catch(e)  
    {  
    document.write ("Error Code: ");  
    document.write (e.number & 0xFFFF)  
    document.write ("<br />");  
  
    document.write ("Facility Code: ")  
    document.write(e.number>>16 & 0x1FFF)  
    document.write ("<br />");  
  
    document.write ("Error Message: ")  
    document.write (e.message)  
    }  
```  
  
## <a name="example"></a>예제  
 이 코드의 출력은 다음과 같습니다.  
  
```JavaScript  
Error Code: 5009  
Facility Code: 10  
Error Message: 'y' is undefined  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
 **적용 대상**: [Error 개체](../../javascript/reference/error-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [description 속성 (Error)](../../javascript/reference/description-property-error-javascript.md)   
 [message 속성 (Error)](../../javascript/reference/message-property-error-javascript.md)   
 [name 속성(Error)](../../javascript/reference/name-property-error-javascript.md)