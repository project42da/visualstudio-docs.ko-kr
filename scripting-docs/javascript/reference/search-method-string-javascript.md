---
title: "search 메서드 (String) (JavaScript) | Microsoft Docs"
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
- search
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- search method
ms.assetid: 1cae0fbc-3319-4327-ba4e-d5fa2c4a9ba0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 730fb1604147b56fc5ab1e312bf7a6dfb5487a5a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="search-method-string-javascript"></a>search 메서드(String)(JavaScript)
정규식 검색에서 첫 번째 부분 문자열 일치를 찾습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
stringObj.search(rgExp)   
```  
  
## <a name="parameters"></a>매개 변수  
 `stringObj`  
 필수 요소. `String` 개체 또는 문자열 검색을 수행 하려면 리터럴입니다.  
  
 `rgExp`  
 필수 요소. 인스턴스는 **정규식** 정규식 패턴 및 적용 가능한 플래그를 포함 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 일치 하는 항목이 없는 경우는 **검색** 메서드는 첫 번째 일치 문자열의 시작에서 오프셋을 나타내는 정수 값 반환 합니다. 일치 항목이 없는 경우-1을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 설정할 수도 있습니다는 `i` 검색에서 대/소문자 구분 되도록 하는 플래그입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **검색** 메서드.  
  
```JavaScript  
var src = "is but a Dream within a dream";  
var re = /dream/;  
var pos = src.search(re);  
document.write(pos);  
document.write("<br/>");  
  
re = /dream/i;  
pos = src.search(re);  
document.write(pos);  
  
// Output:   
// 24   
// 9  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [문자열 개체](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [exec 메서드 (Regular Expression)](../../javascript/reference/exec-method-regular-expression-javascript.md)   
 [match 메서드 (String)](../../javascript/reference/match-method-string-javascript.md)   
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [정규식 구문 (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [replace 메서드 (String)](../../javascript/reference/replace-method-string-javascript.md)   
 [테스트 메서드 (Regular Expression)](../../javascript/reference/test-method-regular-expression-javascript.md)   
 [정규식 프로그래밍 (JavaScript)](http://msdn.microsoft.com/en-us/3b62e27c-4f07-4726-a95b-6e841807bfaf)