---
title: "Regular Expression 개체(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "RegularExpression_JavaScript"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "RegExp 개체, 개요"
  - "Regular Expression 개체"
  - "정규식, RegExp 개체"
ms.assetid: 346aa83e-a045-47ea-acae-b42c7b121534
caps.latest.revision: 21
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 21
---
# Regular Expression 개체(JavaScript)
패턴을 적용하는 방법을 식별하는 플래그와 함께 정규식 패턴을 포함하는 개체입니다.  
  
## 구문  
  
```  
re = /pattern/[flags]  
```  
  
## 구문  
  
```  
re = new RegExp("pattern"[,"flags"])   
```  
  
## 매개 변수  
 *re*  
 필수.  정규식 패턴이 할당되는 변수 이름입니다.  
  
 *pattern*  
 필수.  사용할 정규식 패턴입니다.  구문 1을 사용하는 경우 패턴을 "\/" 문자로 구분합니다.  구문 2를 사용하는 경우 패턴을 따옴표로 묶습니다.  
  
 `flags`  
 선택 사항입니다.  구문 2를 사용하는 경우 플래그를 따옴표로 묶습니다.  결합할 수 있는 사용 가능한 플래그는 다음과 같습니다.  
  
-   g\(모든 *pattern*에 대한 전역 검색\)  
  
-   i\(대\/소문자 무시\)  
  
-   m\(여러 줄 검색\)  
  
-   u\(유니코드\), EcmaScript 6 [유니코드 기능](../../javascript/advanced/special-characters-javascript.md)을 사용하도록 설정합니다.  [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)]에서만 지원됩니다.  
  
-   y\(고정 일치\), 정규식의 `lastIndex` 속성에서 일치 항목을 검색합니다\(이후 인덱스에서는 검색하지 않음\).  [!INCLUDE[jsv12textExp](../../javascript/includes/jsv12textexp-md.md)]에서 지원됩니다.  
  
## 설명  
 **Regular Expression** 개체를 전역 `RegExp` 개체와 혼동해서는 안 됩니다.  동일한 것 같지만 서로 다른 고유한 개체입니다.  **Regular Expression** 개체의 속성에는 하나의 특정 **Regular Expression** 인스턴스에 대한 정보만 포함되는 반면, 전역 `RegExp` 개체의 속성에는 발생 시 각 일치 항목에 대해 지속적으로 업데이트되는 정보가 포함됩니다.  
  
 **Regular Expression** 개체는 문자열에서 문자 조합을 검색할 때 사용되는 패턴을 저장합니다.  **Regular Expression** 개체가 생성된 후 문자열 메서드에 전달되거나 문자열이 정규식 메서드 중 하나에 전달됩니다.  가장 최근에 수행된 검색에 대한 정보는 전역 `RegExp` 개체에 저장됩니다.  
  
 검색 문자열을 미리 알고 있는 경우 구문 1을 사용합니다.  검색 문자열이 자주 변경되거나 사용자 입력에서 가져오는 문자열과 같이 알 수 없는 경우 구문 2를 사용합니다.  
  
 *pattern* 인수는 사용 전에 내부 형식으로 컴파일됩니다.  구문 1의 경우 *pattern*이 스크립트를 로드할 때 컴파일됩니다.  구문 2의 경우 *pattern*이 사용 직전이나 **compile** 메서드를 호출할 때 컴파일됩니다.  
  
## 예제  
 다음 예제에서는 연결된 해당 플래그와 함께 정규식 패턴을 \(다시\) 포함하는 개체를 만들어 **Regular Expression** 개체를 사용하는 방법을 보여 줍니다.  이 경우, 결과로 생성된 **Regular Expression** 개체는 `match` 메서드에서 사용됩니다.  
  
```javascript  
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
  
## 예제  
 다음 예제에서는 여러 인스턴스를 검색하도록 정규식 패턴을 업데이트합니다.  
  
```javascript  
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
  
## 예제  
 \/y 플래그를 사용하는 경우 성공적으로 일치하면 `lastindex`를 마지막 일치 항목 뒤의 다음 문자 인덱스로 업데이트합니다.  일치에 실패하면 `lastindex`를 0으로 다시 설정합니다.  
  
 다음 예제에서는 \/y 플래그 및 `lastIndex` 속성을 사용하여 특정 인덱스에서 일치 항목을 검색합니다.  
  
```javascript  
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
## 속성  
 [global 속성](../../javascript/reference/global-property-regular-expression-javascript.md) &#124; [ignoreCase 속성](../../javascript/reference/ignorecase-property-regular-expression-javascript.md) &#124; [multiline 속성](../../javascript/reference/multiline-property-regular-expression-javascript.md) &#124; [source 속성](../../javascript/reference/source-property-regular-expression-javascript.md)  
  
<a name="js56jsobjregexpressionmeth"></a>   
## 메서드  
 [compile 메서드](../../javascript/reference/compile-method-regular-expression-javascript.md) &#124; [exec 메서드](../../javascript/reference/exec-method-regular-expression-javascript.md) &#124; [test 메서드](../../javascript/reference/test-method-regular-expression-javascript.md)  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 u 플래그는 [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)]에서 지원됩니다.  
  
 y 플래그는 [!INCLUDE[jsv12textExp](../../javascript/includes/jsv12textexp-md.md)]에서 지원됩니다.  
  
## 참고 항목  
 [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)   
 [Regular Expression Syntax \(JavaScript\)](http://msdn.microsoft.com/ko-kr/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [String 개체](../../javascript/reference/string-object-javascript.md)