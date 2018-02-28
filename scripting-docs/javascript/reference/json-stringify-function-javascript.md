---
title: "JSON.stringify 함수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- stringify method
ms.assetid: 0fafaf3b-c29b-46dc-b65b-ca223064a1d0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3539bb003ed20a3ff7586e42466bf7c47165b83f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsonstringify-function-javascript"></a>JSON.stringify 함수(JavaScript)
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 값을 JSON(JavaScript Object Notation) 문자열로 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
JSON.stringify(  
value [, replacer] [, space])  
```  
  
## <a name="parameters"></a>매개 변수  
 `value`  
 필수 요소. [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 값은 일반적으로 변환할 개체 또는 배열입니다.  
  
 `replacer`  
 선택 사항입니다. 결과를 변환하는 함수 또는 배열입니다.  
  
 `replacer`가 함수이면 `JSON.stringify`는 키와 각 멤버의 값을 전달하여 함수를 호출합니다. 반환 값은 원래 값 대신 사용됩니다. 함수가 `undefined`를 반환하면 멤버가 제외됩니다. 루트 개체의 키는 빈 문자열인 ""입니다.  
  
 `replacer`가 배열이면 배열에 키 값이 있는 멤버만 변환됩니다. 멤버가 변환되는 순서는 배열의 키 순서와 같습니다. `replacer` 배열은 `value` 인수도 배열인 경우 무시됩니다.  
  
 `space`  
 선택 사항입니다. 읽기 쉽도록 들여쓰기, 공백, 줄 바꿈 문자를 반환 값 JSON 텍스트에 추가합니다.  
  
 `space`가 생략되면 반환 값 텍스트가 추가 공백 없이 생성됩니다.  
  
 `space`가 숫자이면 반환 값 텍스트가 각 수준의 지정된 공백 수로 들여쓰기됩니다. `space`가 10보다 크면 텍스트가 10칸 들여쓰기됩니다.  
  
 `space`가 '\t'와 같이 빈 문자열이 아니면 반환 값 텍스트가 각 수준에서 문자열의 문자로 들여쓰기됩니다.  
  
 `space`가 10자보다 긴 문자열이면 처음 10자가 사용됩니다.  
  
## <a name="return-value"></a>반환 값  
 JSON 텍스트를 포함하는 문자열입니다.  
  
## <a name="exceptions"></a>예외  
  
|예외|조건|  
|---------------|---------------|  
|[치환 인수가 잘못되었습니다.](../../javascript/misc/invalid-replacer-argument.md)|`replacer` 인수는 함수 또는 배열이 아닙니다.|  
|[값 인수에 순환 참조를 사용하는 것은 지원되지 않습니다.](../../javascript/misc/circular-reference-in-value-argument-not-supported.md)|`value` 인수는 순환 참조를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 `value`에 `toJSON` 메서드가 있으면 `JSON.stringify` 함수는 해당 메서드의 반환 값을 사용합니다. `toJSON` 메서드의 반환 값이 `undefined`이면 멤버가 변환되지 않습니다. 이 경우 개체가 JSON 표현을 결정할 수 있습니다.  
  
 `undefined`와 같은 JSON 표현이 없는 값은 변환되지 않습니다. 이러한 값은 개체에서 삭제됩니다. 배열에서 이러한 값은 null로 바뀝니다.  
  
 문자열 값은 큰따옴표로 시작하고 끝납니다. 백슬래시로 이스케이프되어야 하는 문자를 제외한 모든 유니코드 문자는 큰따옴표로 묶을 수 있습니다. 다음 문자는 백슬래시 다음에 와야 합니다.  
  
-   큰따옴표(")  
  
-   백슬래시(\\)  
  
-   백스페이스(b)  
  
-   용지 공급(f)  
  
-   줄 바꿈(n)  
  
-   캐리지 리턴(r)  
  
-   가로 탭(t)  
  
-   네 자리 16진수(uhhhh)  
  
## <a name="order-of-execution"></a>실행 순서  
 Serialization 프로세스 중 `toJSON` 메서드가 `value` 인수에 있으면 `JSON.stringify`는 먼저 `toJSON` 메서드를 호출합니다. 메서드가 없으면 원래 값이 사용됩니다. 다음으로 `replacer` 인수가 제공되면 값(원래 값 또는 `toJSON` 반환 값)은 `replacer` 인수의 반환 값으로 바뀝니다. 마지막으로 최종 JSON 텍스트를 생성하기 위해 선택적인 `space` 인수를 기반으로 하는 값에 공백이 추가됩니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `JSON.stringify`를 사용하여 `contact` 개체를 JSON 텍스트로 변환합니다. `memberfilter` 배열이 정의되어 `surname` 및 `phone` 멤버만 변환됩니다. `firstname` 멤버는 생략됩니다.  
  
```JavaScript  
var contact = new Object();  
contact.firstname = "Jesper";  
contact.surname = "Aaberg";  
contact.phone = ["555-0100", "555-0120"];  
  
var memberfilter = new Array();  
memberfilter[0] = "surname";  
memberfilter[1] = "phone";  
var jsonText = JSON.stringify(contact, memberfilter, "\t");  
document.write(jsonText);  
// Output:   
// { "surname": "Aaberg", "phone": [ "555-0100", "555-0120" ] }  
```  
  
## <a name="example"></a>예제  
 이 예제에서는 배열이 있는 `JSON.stringify`를 사용합니다. `replaceToUpper` 함수는 배열의 모든 문자열을 대문자로 변환합니다.  
  
```JavaScript  
var continents = new Array();  
continents[0] = "Europe";  
continents[1] = "Asia";  
continents[2] = "Australia";  
continents[3] = "Antarctica";  
continents[4] = "North America";  
continents[5] = "South America";  
continents[6] = "Africa";  
  
var jsonText = JSON.stringify(continents, replaceToUpper);  
  
function replaceToUpper(key, value) {  
    return value.toString().toUpperCase();  
}  
  
//Output:  
// "EUROPE,ASIA,AUSTRALIA,ANTARCTICA,NORTH AMERICA,SOUTH AMERICA,AFRICA"  
  
```  
  
## <a name="example"></a>예제  
 이 예제에서는 `toJSON` 메서드를 사용하여 문자열 값을 대문자로 변환합니다.  
  
```JavaScript  
var contact = new Object();   
contact.firstname = "Jesper";  
contact.surname = "Aaberg";  
contact.phone = ["555-0100", "555-0120"];  
  
contact.toJSON = function(key)  
 {  
    var replacement = new Object();  
    for (var val in this)  
    {  
        if (typeof (this[val]) === 'string')  
            replacement[val] = this[val].toUpperCase();  
        else  
            replacement[val] = this[val]  
    }  
    return replacement;  
};  
  
var jsonText = JSON.stringify(contact);  
document.write(jsonText);  
  
// Output:  
{"firstname":"JESPER","surname":"AABERG","phone":["555-0100","555-0120"]}  
  
'{"firstname":"JESPER","surname":"AABERG","phone":["555-0100","555-0120"]}'  
*/  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv58](../../javascript/reference/includes/jsv58-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [JSON.parse 함수](../../javascript/reference/json-parse-function-javascript.md)   
 [toJSON 메서드 (Date)](../../javascript/reference/tojson-method-date-javascript.md)   
 [피드 판독기 샘플 응용 프로그램 (Windows 스토어)](http://code.msdn.microsoft.com/Feed-reader-sample-99d68cf8)