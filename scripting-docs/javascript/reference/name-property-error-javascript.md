---
title: "name 속성 (Error) (JavaScript) | Microsoft Docs"
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
- name
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Name property
- name property, error name
ms.assetid: 94df2d6b-f1a1-4931-a956-0a930cb87f76
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1a12157b4c467499fab23f7c4cb1be91e9ac5440
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="name-property-error-javascript"></a>name 속성(Error)(JavaScript)
오류의 이름을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
errorObj.  
name  
  
```  
  
## <a name="parameters"></a>매개 변수  
 `errorObj`  
 필수 요소. 인스턴스 `Error` 개체입니다.  
  
## <a name="remarks"></a>설명  
 **이름** 속성 오류가의 이름 또는 예외 형식을 반환 합니다. 런타임 오류가 발생 하는 name 속성은 다음 기본 예외 형식 중 하나로 설정 됩니다.  
  
|예외 형식|의미|  
|--------------------|-------------|  
|ConversionError|이 오류는 개체를에 변환할 수 없는 항목으로 변환 하려고 할 때마다 발생 합니다.|  
|RangeError|이 오류는 함수 인수는 허용 범위를 초과 했습니다를에 제공 될 경우 발생 합니다. 구성 하려고 할 경우이 오류가 발생 하는 예를 들어 한 `Array` 길이가 유효한 양의 정수가 아닌 개체를 합니다.|  
|ReferenceError|이 오류는 잘못 된 참조가 발견 될 때 발생 합니다. 이 오류가 발생 합니다, 예를 들어, 예상한 참조가 경우 `null`합니다.|  
|RegExpError|이 오류는 정규식에 컴파일 오류가 발생 하는 경우에 발생 합니다. 그러나 정규식이 컴파일되면이 오류가 발생할 수 없습니다. 이 예제에서는 때 발생 합니다, 예를 들어, 정규식이 잘못 된 구문이 나 이외의 플래그가 패턴으로 선언 **i**, **g**, 또는 **m**, 포함 된 경우 또는 같은 플래그가 두 번 이상.|  
|SyntaxError|소스 텍스트 구문 분석 되 고 해당 소스 텍스트는 올바른 구문을 따르지 않습니다이 오류가 발생 합니다. 하는 경우,이 오류가 발생 합니다는 `eval` 인수를 프로그램 텍스트가 함수를 호출 합니다.|  
|TypeError|이 오류는 피연산자의 실제 형식이 필요한 형식과 일치 하지 않을 때마다 발생 합니다. 이 오류가 발생할 때의 예로 함수를 호출할 것에 함수 또는 호출을 지원 하지 않습니다.|  
|URIError|이 오류는 잘못 된 표시기 URI (Uniform Resource) 검색 되 면 발생 합니다. 이 오류는 예를 들어, 인코딩 또는 디코딩할 문자열에 잘못 된 문자 발견 되 면 발생 합니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 TypeError 예외를 throw 하 고 오류 이름과 해당 메시지를 표시 합니다.  
  
```JavaScript  
try  
{  
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
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [Error 개체](../../javascript/reference/error-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [description 속성 (Error)](../../javascript/reference/description-property-error-javascript.md)   
 [message 속성 (Error)](../../javascript/reference/message-property-error-javascript.md)   
 [number 속성(Error)](../../javascript/reference/number-property-error-javascript.md)