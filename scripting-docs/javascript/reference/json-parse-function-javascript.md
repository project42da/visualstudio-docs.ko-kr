---
title: "JSON.parse 함수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: JSON.parse
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- parse JSON method
- JSON.parse method
ms.assetid: 20f00d31-5ab5-4c3c-ab49-2534fc39a9b4
caps.latest.revision: "41"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 519fc733fd42a194fbd7335127ddf9bcf0bdc220
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="jsonparse-function-javascript"></a>JSON.parse 함수(JavaScript)
JSON(JavaScript Object Notation) 문자열을 개체로 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
JSON.parse(text [, reviver])  
```  
  
## <a name="parameters"></a>매개 변수  
 `text`  
 필수 요소. 유효한 JSON 문자열입니다.  
  
 `reviver`  
 선택적 요소. 결과를 변환하는 함수입니다. 이 함수는 개체의 각 멤버에 대해 호출됩니다. 멤버에 중첩된 개체가 포함되어 있으면 중첩된 개체가 부모 개체보다 먼저 변환됩니다. 멤버 각각에 대해 다음이 발생합니다.  
  
-   `reviver` 에서 유효한 값을 반환하면 멤버 값은 변환된 값으로 바뀝니다.  
  
-   `reviver`에서 수신한 값과 동일한 값을 반환하면 멤버 값은 수정되지 않습니다.  
  
-   `reviver`가 `null` 또는 `undefined`를 반환하면 멤버가 삭제됩니다.  
  
## <a name="return-value"></a>반환 값  
 개체 또는 배열입니다.  
  
## <a name="exceptions"></a>예외  
 이 함수로 인해 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 파서 오류("SCRIPT1014: 잘못된 문자입니다.")가 발생하는 경우 입력 텍스트가 JSON 구문을 따르지 않은 것입니다. 오류를 수정하려면 다음 중 하나를 수행합니다.  
  
-   `text` 인수를 수정하여 JSON 구문을 따르도록 합니다. 자세한 내용은 JSON 개체의 [BNF 구문 표기법](http://go.microsoft.com/fwlink/?LinkId=125203) 을 참조하세요.  
  
     예를 들어, 응답이 순수 JSON이 아닌 JSONP 형식으로 된 경우 응답 개체에서 다음 코드를 사용해 보십시오.  
  
    ```JavaScript  
    var fixedResponse = response.responseText.replace(/\\'/g, "'");  
    var jsonObj = JSON.parse(fixedResponse);  
    ```  
  
-   `text` 인수가 `JSON.stringify`와 같은 JSON 규격 구현으로 serialize되는지 확인합니다.  
  
-   실행는 `text` 와 같은 JSON 유효성 검사기의 인수 [JSLint](http://www.jslint.com/) 또는 [CSV로 JSON](https://json-csv.com) 구문 오류를 식별할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 `JSON.parse` 를 사용하여 JSON 문자열을 개체로 변환합니다.  
  
```JavaScript  
var jsontext = '{"firstname":"Jesper","surname":"Aaberg","phone":["555-0100","555-0120"]}';  
var contact = JSON.parse(jsontext);  
document.write(contact.surname + ", " + contact.firstname);  
document.write(contact.phone[1]);  
// Output:  
// Aaberg, Jesper  
// 555-0100  
```  
  
## <a name="example"></a>예  
 다음 예제에서는 `JSON.stringify`를 사용하여 배열을 JSON 문자열로 변환한 다음 `JSON.parse`를 사용하여 문자열을 다시 배열로 변환합니다.  
  
```JavaScript  
var arr = ["a", "b", "c"];  
var str = JSON.stringify(arr);  
document.write(str);  
document.write ("<br/>");  
  
var newArr = JSON.parse(str);  
  
while (newArr.length > 0) {  
    document.write(newArr.pop() + "<br/>");  
}  
  
// Output:  
// ["a","b","c"]  
// c  
// b  
// a  
```  
  
## <a name="example"></a>예  
 `reviver` 함수는 ISO(International Organization for Standardization) 날짜 문자열의 JSON 표현을 UTC(협정 세계시) 형식 `Date` 개체로 변환하는 경우에 사용됩니다. 이 예제에서는 `JSON.parse`를 사용하여 ISO 형식의 날짜 문자열을 deserialize합니다. `dateReviver` 함수는 ISO 날짜 문자열처럼 형식이 지정된 멤버의 `Date` 개체를 반환합니다.  
  
```JavaScript  
var jsontext = '{ "hiredate": "2008-01-01T12:00:00Z", "birthdate": "2008-12-25T12:00:00Z" }';  
var dates = JSON.parse(jsontext, dateReviver);  
document.write(dates.birthdate.toUTCString());  
  
function dateReviver(key, value) {  
    var a;  
    if (typeof value === 'string') {  
        a = /^(\d{4})-(\d{2})-(\d{2})T(\d{2}):(\d{2}):(\d{2}(?:\.\d*)?)Z$/.exec(value);  
        if (a) {  
            return new Date(Date.UTC(+a[1], +a[2] - 1, +a[3], +a[4],  
                            +a[5], +a[6]));  
        }  
    }  
    return value;  
};  
  
// Output:  
// Thu, 25 Dec 2008 12:00:00 UTC  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv58](../../javascript/reference/includes/jsv58-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [JSON.stringify 함수](../../javascript/reference/json-stringify-function-javascript.md)   
 [toJSON 메서드 (Date)](../../javascript/reference/tojson-method-date-javascript.md)   
 [허브 템플릿 샘플 앱 (Windows 스토어)](http://code.msdn.microsoft.com/Hub-template-sample-with-4b70002d)