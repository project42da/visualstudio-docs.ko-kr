---
title: "Regular Expression 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: RegularExpression_JavaScript
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Regular Expression object
- regular expressions, RegExp object
- RegExp object, overview
ms.assetid: 346aa83e-a045-47ea-acae-b42c7b121534
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: df2d07e3b47e315ec804e5a7f20024dc2184eef0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="regular-expression-object-javascript"></a>Regular Expression 개체(JavaScript)
패턴을 적용하는 방법을 식별하는 플래그와 함께 정규식 패턴을 포함하는 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
re = /pattern/[flags]  
```  
  
## <a name="syntax"></a>구문  
  
```  
re = new RegExp("pattern"[,"flags"])   
```  
  
## <a name="parameters"></a>매개 변수  
 *re*  
 필수 요소. 정규식 패턴이 할당되는 변수 이름입니다.  
  
 *패턴*  
 필수 요소. 사용할 정규식 패턴입니다. 구문 1을 사용하는 경우 패턴을 "/" 문자로 구분합니다. 구문 2를 사용하는 경우 패턴을 따옴표로 묶습니다.  
  
 `flags`  
 선택적 요소. 구문 2를 사용하는 경우 플래그를 따옴표로 묶습니다. 결합할 수 있는 사용 가능한 플래그는 다음과 같습니다.  
  
-   g (의 모든 항목에 대 한 전역 검색 *패턴*)  
  
-   i(대/소문자 무시)  
  
-   m(여러 줄 검색)  
  
-   u (유니코드), EcmaScript 6을 사용 하면 [유니코드 기능](../../javascript/advanced/special-characters-javascript.md)합니다. [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)]에서만 지원됩니다.  
  
-   y(고정 일치), 정규식의 `lastIndex` 속성에서 일치 항목을 검색합니다(이후 인덱스에서는 검색하지 않음). [!INCLUDE[jsv12textExp](../../javascript/includes/jsv12textexp-md.md)]에서 지원됩니다.  
  
## <a name="remarks"></a>설명  
 **정규식** 개체 전역와 혼동 해서는 안 `RegExp` 개체입니다. 동일한 것 같지만 서로 다른 고유한 개체입니다. 속성에서 **정규식** 개체에는 하나의 특정에 대 한 정보만 포함 **정규식** 의 전역 속성 하는 동안 인스턴스 `RegExp` 개체 포함 발생 시 각 일치 항목에 대 한 정보를 지속적으로 업데이트 합니다.  
  
 **정규식** 개체는 문자열에서 문자 조합을 검색할 때 사용 되는 패턴을 저장 합니다. 후의 **정규식** 개체가 만들어질, 문자열 메서드에 전달 되거나 또는 문자열이 정규식 메서드 중 하나에 전달 됩니다. 가장 최근에 수행된 검색에 대한 정보는 전역 `RegExp` 개체에 저장됩니다.  
  
 검색 문자열을 미리 알고 있는 경우 구문 1을 사용합니다. 검색 문자열이 자주 변경되거나 사용자 입력에서 가져오는 문자열과 같이 알 수 없는 경우 구문 2를 사용합니다.  
  
 *패턴* 인수는 사용 전에 내부 형식으로 컴파일됩니다. 구문 1 *패턴* 이 스크립트를 로드할 때 컴파일됩니다. 구문 2 *패턴* 사용 직전 컴파일될 때 또는 **컴파일** 메서드를 호출 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **정규식** 개체를 만들어 (다시) 연결 된 해당 플래그와 함께 정규식 패턴을 포함 하는 개체입니다. 이 경우, 결과 **정규식** 가 개체에 사용 된 `match` 메서드:  
  
```JavaScript  
var s = "through the pages of the book";  
  
// Create regular expression pattern.  
var re = new RegExp("the", "i");  
  
// Attempt match on search string.  
var r = s.match(re);     
  
// Return first occurrence of "the".  
if(console && console.log) {  
    console.log(r);  
}  
  
// Output:  
//   
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 여러 인스턴스를 검색하도록 정규식 패턴을 업데이트합니다.  
  
```JavaScript  
// Create regular expression pattern using the i and g flags.  
var re = new RegExp("the", "ig");  
  
// Attempt match on search string.  
var r = s.match(re);     
  
// Return the two occurrences of "the".  
if(console && console.log) {  
    console.log(r.length);  
    console.log(r);  
}  
  
// Output:  
// 2  
// [object Array] ["the", "the"]  
```  
  
## <a name="example"></a>예제  
 /y 플래그를 사용하는 경우 성공적으로 일치하면 `lastindex`를 마지막 일치 항목 뒤의 다음 문자 인덱스로 업데이트합니다. 일치에 실패하면 `lastindex`를 0으로 다시 설정합니다.  
  
 다음 예제에서는 /y 플래그 및 `lastIndex` 속성을 사용하여 특정 인덱스에서 일치 항목을 검색합니다.  
  
```JavaScript  
// Create regular expression pattern using the i and y flags.  
var re = new RegExp("the", "iy");  
  
// Set the lastIndex property and attempt a match  
// at the specified index.  
re.lastIndex = 20;  
var r = s.match(re);     
  
// No matches returned.  
if(console && console.log) {  
    console.log(r);  
}  
// Reset the lastIndex property and attempt a match.  
re.lastIndex = 21;  
var r = s.match(re);  
  
// Return occurrence of "the" starting at index 21.  
if(console && console.log) {  
    console.log(r);  
}  
  
// Output:  
// null  
// [object Array] ["the"]  
```  
  
<a name="js56jsobjregexpressionprop"></a>   
## <a name="properties"></a>속성  
 [전역 속성](../../javascript/reference/global-property-regular-expression-javascript.md) &#124; [ignoreCase 속성](../../javascript/reference/ignorecase-property-regular-expression-javascript.md) &#124; [multiline 속성](../../javascript/reference/multiline-property-regular-expression-javascript.md) &#124; [source 속성](../../javascript/reference/source-property-regular-expression-javascript.md)  
  
<a name="js56jsobjregexpressionmeth"></a>   
## <a name="methods"></a>메서드  
 [compile 메서드](../../javascript/reference/compile-method-regular-expression-javascript.md) &#124; [exec 메서드](../../javascript/reference/exec-method-regular-expression-javascript.md) &#124; [테스트 메서드](../../javascript/reference/test-method-regular-expression-javascript.md)  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 u 플래그는 [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)]에서 지원됩니다.  
  
 y 플래그는 [!INCLUDE[jsv12textExp](../../javascript/includes/jsv12textexp-md.md)]에서 지원됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)   
 [정규식 구문 (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [String 개체](../../javascript/reference/string-object-javascript.md)