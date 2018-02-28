---
title: "문자열 개체 (JavaScript) | Microsoft Docs"
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
- String_JavaScript
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- String object
- String object, overview
ms.assetid: 8063ecd5-5778-4e87-b985-b21420171914
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d58f567bb301b29324fee8ed75fc95fd1a4791ea
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="string-object-javascript"></a>String 개체(JavaScript)
텍스트 문자열을 조작하고 서식을 지정하거나 문자열 안에서 부분 문자열을 결정하고 위치를 지정할 수 있게 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
newString = new String(["stringLiteral"])  
```  
  
## <a name="parameters"></a>매개 변수  
 `newString`  
 필수 요소. `String` 개체가 할당되는 변수 이름입니다.  
  
 `stringLiteral`  
 선택적 요소. 임의의 유니코드 문자 그룹입니다.  
  
## <a name="remarks"></a>설명  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]는 직접 입력할 수 없는 문자를 만들기 위해 문자열에 포함시킬 수 있는 이스케이프 시퀀스를 제공합니다. 예를 들어 `\t`는 탭 문자를 지정합니다. 자세한 내용은 [특수 문자](../../javascript/advanced/special-characters-javascript.md)를 참조하세요.  
  
## <a name="string-literals"></a>문자열 리터럴  
 A *문자열 리터럴을* 은 단일 또는 이중 따옴표로 묶인 0 개 이상의 문자입니다. 문자열 리터럴은 `string`의 기본 데이터 형식입니다. A *String 개체* 사용 하 여 만든는 [new 연산자](../../javascript/reference/new-operator-decrementjavascript.md)의 데이터 형식이 고 `Object`합니다.  
  
 다음 예제에서는 문자열 리터럴의 데이터 형식이 `String` 개체의 데이터 형식과 같지 않음을 보여 줍니다.  
  
```JavaScript  
var strLit = "This is a string literal.";  
var strObj = new String("This is a string object.");  
  
document.write(typeof strLit);  
document.write("<br/>");  
document.write(typeof strObj);  
// Output:  
// string  
// object  
```  
  
## <a name="methods-for-string-literals"></a>문자열 리터럴에 대한 메서드  
 문자열 리터럴에 대해 메서드를 호출할 때 문자열 리터럴은 임시로 문자열 래퍼 개체로 변환됩니다. 문자열 리터럴은 이 문자열 리터럴을 만들 때 `new` 연산자가 사용된 것처럼 처리됩니다.  
  
 다음 예제에서는 문자열 리터럴에 `toUpperCase` 메서드를 적용합니다.  
  
```JavaScript  
var strLit = "This is a string literal.";  
  
var result1 = strLit.toUpperCase();  
  
var result2 = (new String(strLit)).toUpperCase();  
  
document.write(result1);  
document.write("<br/>");  
document.write(result2);  
// Output:   
// THIS IS A STRING LITERAL.  
// THIS IS A STRING LITERAL.  
```  
  
## <a name="accessing-an-individual-character"></a>개별 문자 액세스  
 문자열의 개별 문자에는 읽기 전용의 배열 인덱싱된 속성으로 액세스할 수 있습니다. 이 기능은 [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)]에서 도입되었습니다. 다음 예제에서는 개별 문자열 문자에 액세스합니다.  
  
```JavaScript  
var str = "abcd";  
var result = str[2];  
document.write (result);  
// Output: c  
  
var result = "the"[0];  
document.write(result);  
// Output: t  
```  
  
## <a name="requirements"></a>요구 사항  
 `String Object`는 [!INCLUDE[jsv1text](../../javascript/reference/includes/jsv1text-md.md)]에서 도입되었습니다. 다음 목록의 일부 멤버는 이후 버전에서 도입되었습니다.  
  
<a name="js56jsobjstringprop"></a>   
## <a name="properties"></a>속성  
 다음 표에서는 `String` 개체의 속성을 보여 줍니다.  
  
|속성|설명|  
|--------------|-----------------|  
|[constructor 속성](../../javascript/reference/constructor-property-string.md)|개체를 만드는 함수를 지정합니다.|  
|[length 속성(String)](../../javascript/reference/length-property-string-javascript.md)|`String` 개체의 길이를 반환합니다.|  
|[prototype 속성](../../javascript/reference/prototype-property-string.md)|개체 클래스의 프로토타입에 대한 참조를 반환합니다.|  
  
## <a name="functions"></a>함수  
 다음 표에서는 `String` 개체의 함수를 보여줍니다.  
  
|함수|설명|  
|--------------|-----------------|  
|[String.fromCharCode 함수](../../javascript/reference/string-fromcharcode-function-javascript.md)|여러 유니코드 문자 값에서 문자열을 반환합니다.|  
|[String.fromCodePoint 함수](../../javascript/reference/string-fromcodepoint-function-javascript.md)|유니코드 UTF-16 코드 포인트와 연결된 문자열을 반환합니다.|  
|[String.raw 함수](../../javascript/reference/string-raw-function-javascript.md)|템플릿 문자열의 원시 문자열을 반환합니다.|  
  
<a name="js56jsobjstringmeth"></a>   
## <a name="methods"></a>메서드  
 다음 표에서는 `String` 개체의 메서드를 보여 줍니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[anchor 메서드](../../javascript/reference/html-tag-methods-javascript.md)|텍스트 양 끝에 NAME 특성을 가진 HTML 앵커를 삽입합니다.|  
|[big 메서드](../../javascript/reference/html-tag-methods-javascript.md)|에서는 HTML \<큰 > 텍스트 태그입니다.|  
|[blink 메서드](../../javascript/reference/html-tag-methods-javascript.md)|에서는 HTML \<BLINK > 텍스트 태그입니다.|  
|[bold 메서드](../../javascript/reference/html-tag-methods-javascript.md)|에서는 HTML \<B > 텍스트 태그입니다.|  
|[charAt 메서드](../../javascript/reference/charat-method-string-javascript.md)|지정한 인덱스에 해당하는 문자를 반환합니다.|  
|[charCodeAt 메서드](../../javascript/reference/charcodeat-method-string-javascript.md)|지정한 문자의 유니코드 인코딩을 반환합니다.|  
|[codePointAt 메서드](../../javascript/reference/codepointat-method-string-javascript.md)|유니코드 UTF-16 문자에 대한 코드 포인트를 반환합니다.|  
|[concat 메서드(String)](../../javascript/reference/concat-method-string-javascript.md)|주어진 두 문자열의 연결을 포함하는 문자열을 반환합니다.|  
|[endsWith 메서드](../../javascript/reference/endswith-method-string-javascript.md)|문자열 또는 하위 문자열이 전달된 문자열로 끝나는지 여부를 나타내는 부울 값을 반환합니다.|  
|[includes 메서드](../../javascript/reference/includes-method-string-javascript.md)|전달된 문자열이 문자열 개체에 포함되어 있는지 여부를 나타내는 부울 값을 반환합니다.|  
|[fixed 메서드](../../javascript/reference/html-tag-methods-javascript.md)|에서는 HTML \<TT > 텍스트 태그입니다.|  
|[fontcolor 메서드](../../javascript/reference/html-tag-methods-javascript.md)|에서는 HTML \<글꼴 > 텍스트에 COLOR 특성을 가진 태그입니다.|  
|[fontsize 메서드](../../javascript/reference/html-tag-methods-javascript.md)|에서는 HTML \<글꼴 > 텍스트 주위의 크기 특성으로 태그입니다.|  
|[hasOwnProperty 메서드](../../javascript/reference/hasownproperty-method-object-javascript.md)|개체에 지정된 이름을 가진 속성이 있는지 여부를 나타내는 부울 값을 반환합니다.|  
|[indexOf 메서드(String)](../../javascript/reference/indexof-method-string-javascript.md)|문자열 안에서 부분 문자열이 처음 나오는 문자 위치를 반환합니다.|  
|[isPrototypeOf 메서드](../../javascript/reference/isprototypeof-method-object-javascript.md)|개체가 다른 개체의 프로토타입 체인에 있는지 여부를 나타내는 부울 값을 반환합니다.|  
|[italics 메서드](../../javascript/reference/html-tag-methods-javascript.md)|에서는 HTML \<I > 텍스트 태그입니다.|  
|[lastIndexOf 메서드(String)](../../javascript/reference/lastindexof-method-string-javascript.md)|문자열 내에서 부분 문자열이 마지막으로 나오는 경우를 반환합니다.|  
|[link 메서드](../../javascript/reference/html-tag-methods-javascript.md)|텍스트 양 끝에 HREF 특성을 가진 HTML 앵커를 삽입합니다.|  
|[localeCompare 메서드](../../javascript/reference/localecompare-method-string-javascript.md)|두 문자열의 현재 로캘이 동일한지 여부를 나타내는 값을 반환합니다.|  
|[match 메서드](../../javascript/reference/match-method-string-javascript.md)|제공 된를 사용 하 여 문자열 검색 **정규식** 개체 하 고 결과 배열로 반환 합니다.|  
|[normalize 메서드](../../javascript/reference/normalize-method-string-javascript.md)|지정된 문자열의 유니코드 정규화 형식을 반환합니다.|  
|[propertyIsEnumerable 메서드](../../javascript/reference/propertyisenumerable-method-object-javascript.md)|지정된 속성이 개체의 일부인지 여부 및 열거 가능한지 여부를 나타내는 부울 값을 반환합니다.|  
|[repeat 메서드](../../javascript/reference/repeat-method-string-javascript.md)|지정된 횟수만큼 반복되는 원래 문자열과 같은 값과 함께 새 문자열 개체를 반환합니다.|  
|[replace 메서드](../../javascript/reference/replace-method-string-javascript.md)|정규식을 사용하여 문자열의 텍스트를 바꾸고 결과를 반환합니다.|  
|[search 메서드](../../javascript/reference/search-method-string-javascript.md)|정규식 검색에서 첫 번째로 일치하는 부분 문자열의 위치를 반환합니다.|  
|[slice 메서드(String)](../../javascript/reference/slice-method-string-javascript.md)|문자열의 일정 부분을 반환합니다.|  
|[small 메서드](../../javascript/reference/html-tag-methods-javascript.md)|에서는 HTML \<작은 > 텍스트 태그입니다.|  
|[split 메서드](../../javascript/reference/split-method-string-javascript.md)|문자열을 여러 개의 부분 문자열로 분할할 때 만들어지는 문자열의 배열을 반환합니다.|  
|[startsWith 메서드](../../javascript/reference/startswith-method-string-javascript.md)|문자열 또는 하위 문자열이 전달된 문자열로 시작하는지 여부를 나타내는 부울 값을 반환합니다.|  
|[strike 메서드](../../javascript/reference/html-tag-methods-javascript.md)|에서는 HTML \<STRIKE > 텍스트 태그입니다.|  
|[sub 메서드](../../javascript/reference/html-tag-methods-javascript.md)|에서는 HTML \<하위 > 텍스트 태그입니다.|  
|[substr 메서드](../../javascript/reference/substr-method-string-javascript.md)|지정한 위치에서 시작하고 지정한 길이를 가지는 부분 문자열을 반환합니다.|  
|[substring 메서드](../../javascript/reference/substring-method-string-javascript.md)|`String` 개체 안의 지정된 위치에 있는 부분 문자열을 반환합니다.|  
|[sup 메서드](../../javascript/reference/html-tag-methods-javascript.md)|에서는 HTML \<SUP > 텍스트 태그입니다.|  
|[toLocaleLowerCase 메서드](../../javascript/reference/tolocalelowercase-method-string-javascript.md)|호스트 환경의 현재 로캘을 고려하여 모든 영문자가 소문자로 변환된 문자열을 반환합니다.|  
|[toLocaleString 메서드](../../javascript/reference/tolocalestring-method-object-javascript.md)|현재 로캘을 사용하여 문자열로 변환된 개체를 반환합니다.|  
|[toLocaleUpperCase 메서드](../../javascript/reference/tolocaleuppercase-method-string-javascript.md)|호스트 환경의 현재 로캘을 고려하여 모든 영문자가 대문자로 변환된 문자열을 반환합니다.|  
|[toLowerCase 메서드](../../javascript/reference/tolowercase-method-javascript.md)|모든 영문자가 소문자로 변환된 문자열을 반환합니다.|  
|[toString 메서드](../../javascript/reference/tostring-method-string-1.md)|문자열을 반환합니다.|  
|[toUpperCase 메서드](../../javascript/reference/touppercase-method-string-javascript.md)|모든 영문자가 대문자로 변환된 문자열을 반환합니다.|  
|[trim 메서드](../../javascript/reference/trim-method-string-javascript.md)|선행 및 후행 공백과 줄 종결자 문자가 제거된 문자열을 반환합니다.|  
|[valueOf 메서드](../../javascript/reference/valueof-method-string.md)|문자열을 반환합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [new 연산자](../../javascript/reference/new-operator-decrementjavascript.md)   
 [샘플 앱 스크롤, 이동 및 확대/축소](http://code.msdn.microsoft.com/ie/Scrolling-panning-and-6834aaf9)