---
title: "match 메서드 (String) (JavaScript) | Microsoft Docs"
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
- match
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Match method
ms.assetid: eda9ad27-4f9b-4cb1-8345-a0ae85979ca0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 46727942d73779351f1c0cceaf2eb90a691a8ebe
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="match-method-string-javascript"></a>match 메서드(String)(JavaScript)
String과 정규식을 사용 하 고 해당 검색 결과 포함 하는 배열을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
stringObj.match(rgExp)   
```  
  
## <a name="parameters"></a>매개 변수  
 `stringObj`  
 필수 요소. `String` 개체 또는 문자열 검색을 수행 하려면 리터럴입니다.  
  
 `rgExp`  
 필수 요소. 정규식 패턴 및 적용 가능한 플래그를 포함 하는 정규식 개체입니다. 이 변수 이름 또는 정규식 패턴 및 플래그를 포함 하는 리터럴 문자열도 수 있습니다.  
  
## <a name="remarks"></a>설명  
 경우는 `match` 반환 메서드는 일치 하는 항목을 찾지 못하면 `null`합니다. 일치 하는 항목이 발견 되 면 `match` 배열 및 전역 속성을 반환 `RegExp` 개체가 일치 항목의 결과 반영 하도록 업데이트 됩니다.  
  
 경우 전역 플래그 (`g`)을 설정 하지 않으면 요소를 통해 1 요소는 전체 일치를 포함 하는 배열의 0  *n*  대상 모든 부분 포함 합니다. 이 동작은의 동작과 동일는 [exec 메서드 (Regular Expression)](../../javascript/reference/exec-method-regular-expression-javascript.md) 전역 플래그가 설정 되지 않은 경우. 전역 플래그는 설정, 0-요소  *n*  발생 한 모든 일치 항목을 포함 합니다.  
  
 전역 플래그가 설정 되지 않은 경우, 반환 된 배열에서 `match` 메서드 다음 두 가지 속성이 `input` 및 `index`합니다. `input` 속성은 전체 검색된 문자열을 포함 합니다. `index` 속성은 전체 검색된 문자열에 일치 하는 부분 문자열의 위치를 포함 합니다.  
  
 경우 플래그 `i` 설정 검색은 대/소문자 구분 하지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `match` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var src = "azcafAJAC";  
  
var re = /[a-c]/;  
  
var result = src.match(re);  
  
// The entire match is in array element 0.  
document.write(result[0] + "<br/>");  
  
// Now try the same match with the global flag.  
var reg = /[a-c]/g;  
result = src.match(reg);  
  
// The matches are in elements 0 through n.  
for (var index = 0; index < result.length; index++)  
{  
    document.write ("submatch " + index + ": " +  result[index]);  
    document.write("<br />");  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [문자열 개체](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [exec 메서드 (Regular Expression)](../../javascript/reference/exec-method-regular-expression-javascript.md)   
 [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)   
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [replace 메서드 (String)](../../javascript/reference/replace-method-string-javascript.md)   
 [search 메서드 (String)](../../javascript/reference/search-method-string-javascript.md)   
 [테스트 메서드 (Regular Expression)](../../javascript/reference/test-method-regular-expression-javascript.md)   
 [정규식 프로그래밍 (JavaScript)](http://msdn.microsoft.com/en-us/3b62e27c-4f07-4726-a95b-6e841807bfaf)   
 [교체 및 하위 식 (JavaScript)](http://msdn.microsoft.com/en-us/c59dd3e8-7fee-493e-9123-065af1e651ae)   
 [역참조 (JavaScript)](http://msdn.microsoft.com/en-us/5d8dbd5a-cd03-4548-850b-9d7bad2c839a)