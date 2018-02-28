---
title: "테스트 메서드 (Regular Expression) (JavaScript) | Microsoft Docs"
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
- test
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- test method
ms.assetid: 4f4b6e39-cb1a-4be9-a66f-7b846075580d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 53e2d2c23821cba5149367c7b5a735fa471bf581
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="test-method-regular-expression-javascript"></a>test 메서드(Regular Expression)(JavaScript)
패턴을 검색된 한 문자열에 있는지 여부를 나타내는 부울 값을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
rgExp.test(str)   
```  
  
## <a name="parameters"></a>매개 변수  
 `rgExp`  
 필수 요소. 인스턴스는 **정규식** 정규식 패턴 및 적용 가능한 플래그를 포함 하는 개체입니다.  
  
 `str`  
 필수 요소. 검색을 수행 하려면 기반이 문자열입니다.  
  
## <a name="remarks"></a>설명  
 **테스트** 메서드를 확인 하는 패턴 문자열 내에서 반환 하는 경우 확인 **true** 그렇다면 및 **false** 그렇지 않은 경우.  
  
 전역 속성 `RegExp` 개체에 의해 수정 되지 않습니다는 **테스트** 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **테스트** 메서드. 이 예제를 사용 하는 정규식 패턴 및 문자열 함수를 전달 합니다. 함수 그러면 문자열에서 정규식 패턴과 일치 하는 항목에 대 한 테스트 하 고 해당 검색 결과 나타내는 문자열을 반환 합니다.  
  
```JavaScript  
function TestDemo(re, teststring)  
{  
   // Test string for existence of regular expression.  
   var found = re.test(teststring)  
  
   // Format the output.  
   var s = "";  
   s += "'" + teststring + "'"  
  
   if (found)  
      s += " contains ";  
   else  
      s += " does not contain ";  
  
   s += "'" + re.source + "'"  
   return(s);  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)   
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [정규식 구문 (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)