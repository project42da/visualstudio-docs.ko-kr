---
title: "lastIndex 속성 (RegExp) (JavaScript) | Microsoft Docs"
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
- lastIndex
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- lastIndex property
ms.assetid: c8ae2a13-6dff-4cbe-b662-aca3d66c2a7f
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5e24fe14d335e1494b13518543f56025625de0b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="lastindex-property-regexp-javascript"></a>lastIndex 속성(RegExp)(JavaScript)
검색된 문자열에 다음 검색을 시작할 문자 위치를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
RegExp.lastIndex  
```  
  
## <a name="remarks"></a>설명  
 이 속성에 연결 된 개체는 항상 전역 `RegExp` 개체입니다.  
  
 `lastIndex` 속성은 0, 즉, 첫 번째 문자의 인덱스는 0입니다. 초기 값은-1입니다. 성공적으로 일치 하는 때마다 해당 값을 수정 합니다.  
  
 `lastIndex` 속성을 수정 하 여는 `exec` 및 **테스트** 의 메서드는 `RegExp` 개체 및 `match`, **대체**, 및 **분할**의 메서드는 `String` 개체입니다.  
  
 값에는 다음 규칙이 적용 `lastIndex`:  
  
-   일치 항목이 없는 경우 `lastIndex` -1로 설정 합니다.  
  
-   경우 `lastIndex` 문자열의 길이 보다 크면 **테스트** 및 `exec` 실패 및 `lastIndex` -1로 설정 합니다.  
  
-   경우 `lastIndex` 패턴이 빈 문자열과 일치 하는 경우 정규식 일치 항목이 문자열의 길이 같습니다. 그렇지 않으면 검색이 실패 하 고 `lastIndex` -1로 다시 설정 됩니다.  
  
-   그렇지 않으면 `lastIndex` 최근에 가장 일치 하는 다음 위치를 설정 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `lastIndex` 속성입니다. 이 함수는 검색 문자열을 반복 하 고 인쇄는 **인덱스** 및 `lastIndex` 문자열에서 각 단어에 대 한 값입니다.  
  
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
      document.write (arr.index + "-" + re.lastIndex + " ");  
      document.write (arr);  
      }  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [정규식 구문 (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)