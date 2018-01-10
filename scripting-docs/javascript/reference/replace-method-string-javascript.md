---
title: "replace 메서드 (String) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: replace
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- replacing strings
- Replace method
ms.assetid: 5f0e4765-df4d-4887-bd09-efe5e58251bf
caps.latest.revision: "28"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 82894a5d7f92c8231a6ba3a1948369fb2c819a6d
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2018
---
# <a name="replace-method-string-javascript"></a>replace 메서드(String)(JavaScript)
정규식이나 검색 문자열을 사용하여 문자열에서 텍스트를 바꿉니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
stringObj.replace(rgExp, replaceText)  
```  
  
## <a name="parameters"></a>매개 변수  
 `stringObj`  
 필수. 바꾸기를 수행할 `String` 개체 또는 문자열 리터럴입니다. 이 문자열은에 의해 수정 되지는 **대체** 메서드. 이 메서드의 반환 값은 바꾸기로 생성된 문자열입니다.  
  
 `rgExp`  
 필수. 인스턴스는 **정규식** 정규식 패턴 및 적용 가능한 플래그를 포함 하는 개체입니다. 또한 정규식을 나타내는 `String` 개체 또는 문자열 리터럴일 수도 있습니다. 경우 `rgExp` 의 인스턴스가 아닌 한 **정규식** 개체를 문자열로 변환 됩니다 및 결과 대 한 정확한 검색 이루어집니다; 문자열을 정규식으로 변환 하려고 시도 하지 합니다.  
  
 `replaceText`  
 필수. `String`의 `rgExp`와 일치하는 항목을 검색할 때마다 대체할 텍스트가 포함된 `stringObj` 개체 또는 문자열 리터럴입니다. [!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] 이상에서 `replaceText` 인수는 대체 텍스트를 반환하는 함수일 수도 있습니다.  
  
## <a name="return-value"></a>반환 값  
 결과 **대체** 방법은 사본을 `stringObj` 지정 된 대체 후 합니다.  
  
## <a name="remarks"></a>설명  
 다음의 일치 변수 중 하나를 사용하여 최근의 일치 대상과 원본 문자열을 확인할 수 있습니다. 일치 변수는 대체 문자열을 동적으로 결정해야 하는 텍스트 대체에 사용할 수 있습니다.  
  
|문자|의미|  
|----------------|-------------|  
|**$$**|`$`([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] 이상)|  
|**$&**|전체 패턴이 일치한 `stringObj`의 부분을 지정합니다. ([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] 이상)|  
|`$``|부분을 지정 `stringObj` 하 여 표시 된 일치 항목 앞에  **$&** 합니다. ([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] 이상)|  
|`$'`|부분을 지정 `stringObj` 하 여 표시 된 일치 항목 다음에 오는  **$&** 합니다. ([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] 이상)|  
|`$`  ***n***| *n* 번째 캡처된 부분 일치, 여기서  *n*  은 1부터 9 까지의 한 자리 10 진수입니다. ([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] 이상)|  
|`$`  ***nn***| *nn* 번째 캡처된 부분 일치, 여기서  *nn*  01부터 99 까지의 두 자리 10 진수 수입니다. ([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] 이상)|  
  
 경우 `replaceText` 는 다음으로 일치 하는 각 부분 문자열 함수는 호출 된 함수, *m* + 3 개 있는 *m* 에서 왼쪽 캡처 괄호의 수는 `rgExp`합니다. 첫 번째 인수는 일치한 부분 문자열입니다. 다음 *m* 인수는 모든 검색에서 결과입니다. 인수 *m* + 2는 내의 오프셋 `stringObj` 일치가 발생 한 및 인수 *m* + 3은 `stringObj`합니다. 결과는 일치하는 각 부분 문자열을 함수 호출의 해당 반환 값으로 대체하여 생성되는 문자열 값입니다.  
  
 **대체** 의 전역 속성을 업데이트 하는 메서드 `RegExp` 개체입니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 **대체** "the"의 모든 인스턴스를 "a"입니다. 바꾸려면 메서드  
  
```JavaScript  
var s = "the batter hit the ball with the bat";  
  
// Replace "the" with "a".  
var re = /the/g;  
var result = s.replace(re, "a");  
document.write(result);  
// Output: a batter hit a ball with a bat  
```  
  
 또한는 **대체** 메서드는 패턴에서 하위 식을 대체 합니다. 다음 예제에서는 문자열의 각 단어 쌍을 바꿉니다.  
  
```JavaScript  
  
var s = "The quick brown fox jumped over the lazy dog.";  
var re = /(\S+)(\s+)(\S+)/g;  
// Exchange each pair of words.  
var result = s.replace(re, "$3$2$1");  
document.write(result);  
  
// Output:  quick The fox brown over jumped lazy the dog.  
```  
  
 [!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] 이상에서 작동하는 다음 예제에서는 대체 텍스트를 반환하는 함수를 사용하는 방법을 보여줍니다. 이 예제에서는 "F" 앞의 숫자를 모두 섭씨로 변환하여 교체합니다.  
  
```JavaScript  
function f2c(s1) {  
    // Initialize pattern.  
    var test = /(\d+(\.\d*)?)F\b/g;  
  
    // Use a function for the replacement.  
    var s2 = s1.replace(test,  
      function($0,$1,$2)  
           {   
           return((($1-32) * 5/9) + "C");  
           }  
        )  
    return s2;  
}  
document.write(f2c("Water freezes at 32F and boils at 212F."));  
  
// Output: Water freezes at 0C and boils at 100C.  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [문자열 개체](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [exec 메서드 (Regular Expression)](../../javascript/reference/exec-method-regular-expression-javascript.md)   
 [match 메서드 (String)](../../javascript/reference/match-method-string-javascript.md)   
 [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)   
 [search 메서드 (String)](../../javascript/reference/search-method-string-javascript.md)   
 [테스트 메서드 (Regular Expression)](../../javascript/reference/test-method-regular-expression-javascript.md)   
 [정규식 프로그래밍 (JavaScript)](http://msdn.microsoft.com/en-us/3b62e27c-4f07-4726-a95b-6e841807bfaf)   
 [교체 및 하위 식 (JavaScript)](http://msdn.microsoft.com/en-us/c59dd3e8-7fee-493e-9123-065af1e651ae)   
 [역참조 (JavaScript)](http://msdn.microsoft.com/en-us/5d8dbd5a-cd03-4548-850b-9d7bad2c839a)   
 [HTML5 끌어서 놓기 샘플 앱](http://code.msdn.microsoft.com/Drag-and-drop-e2701a72)