---
title: "exec 메서드 (Regular Expression) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: exec
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- matching strings
- Exec method
ms.assetid: 83092452-60cc-4218-b4ae-af9e3cb96c34
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 426cc1a8162b03090289cf737a03d64a75df77e9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="exec-method-regular-expression-javascript"></a>exec 메서드(Regular Expression)(JavaScript)
정규식 패턴을 사용 하는 문자열에서 검색을 실행 하 고 해당 검색 결과 포함 하는 배열을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
rgExp.exec(str)   
```  
  
## <a name="parameters"></a>매개 변수  
 `rgExp`  
 필수 요소. 인스턴스는 **정규식** 정규식 패턴 및 적용 가능한 플래그를 포함 하는 개체입니다.  
  
 `str`  
 필수 요소. `String` 개체 또는 문자열 검색을 수행 하려면 리터럴입니다.  
  
## <a name="remarks"></a>설명  
 경우는 `exec` 반환 메서드는 일치 하는 항목을 찾지 못하면 `null`합니다. 일치 하는 항목이 발견 되 면 `exec` 배열 및 전역 속성을 반환 `RegExp` 개체가 일치 항목의 결과 반영 하도록 업데이트 됩니다. 1-요소는 전체 일치를 포함 하는 배열의 요소 0  *n*  대상 일치 항목 내에서 발생 한 모든 부분 포함 합니다. 이 동작은의 동작과 동일는 `match` 전역 플래그 없이 메서드 (**g**) 설정 합니다.  
  
 정규식에 대 한 전역 플래그를 설정 하는 경우 `exec` 의 값이 지정 된 위치에서 시작 하는 문자열을 검색 `lastIndex`합니다. 전역 플래그를 설정 하지 않으면 `exec` 의 값을 무시 `lastIndex` 문자열의 시작 부분부터 검색 합니다.  
  
 반환 된 배열에서 `exec` 메서드에 세 가지 속성 **입력**, **인덱스** 및 **lastIndex 합니다.** **입력** 속성은 전체 검색된 문자열을 포함 합니다. **인덱스** 속성은 전체 검색된 문자열에 일치 하는 부분 문자열의 위치를 포함 합니다. `lastIndex` 속성의 마지막 문자는 일치 항목의 다음 위치를 포함 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `exec` 메서드:  
  
```JavaScript  
function RegExpTest()  
{  
   var ver = Number(ScriptEngineMajorVersion() + "." + ScriptEngineMinorVersion())  
   if (ver < 5.5)  
   {  
      document.write("You need a newer version of JavaScript for this to work");  
      return;  
   }  
  
   var src = "The quick brown fox jumps over the lazy dog.";  
  
   // Create regular expression pattern with a global flag.  
   var re = /\w+/g;  
  
   // Get the next word, starting at the position of lastindex.  
   var arr;  
   while ((arr = re.exec(src)) != null)  
      {  
      // New line:  
      document.write ("<br />");    
      document.write (arr.index + "-" + arr.lastIndex + " ");  
      document.write (arr[0]);  
      }  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [match 메서드 (String)](../../javascript/reference/match-method-string-javascript.md)   
 [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)   
 [정규식 구문 (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [search 메서드 (String)](../../javascript/reference/search-method-string-javascript.md)   
 [테스트 메서드 (Regular Expression)](../../javascript/reference/test-method-regular-expression-javascript.md)   
 [정규식 프로그래밍 (JavaScript)](http://msdn.microsoft.com/en-us/3b62e27c-4f07-4726-a95b-6e841807bfaf)