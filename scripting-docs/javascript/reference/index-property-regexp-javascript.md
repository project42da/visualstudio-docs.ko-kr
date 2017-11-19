---
title: "index 속성 (RegExp) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: index
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Index property
- matching strings
ms.assetid: d8be1ef6-1bf2-43cd-b0b5-567a61eabaad
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9c6b11a5caf6e727b4d525b9a2d51eddd4542bc4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="index-property-regexp-javascript"></a>index 속성(RegExp)(JavaScript)
검색된 한 문자열에서 처음으로 일치 하는 부분이 시작 문자 위치를 반환 합니다. 읽기 전용입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
RegExp.index   
```  
  
## <a name="remarks"></a>설명  
 이 속성에 연결 된 개체는 항상 전역 `RegExp` 개체입니다.  
  
 **인덱스** 속성은 0부터 시작 합니다. 초기 값은 **인덱스** 속성이-1입니다. 값이 성공적으로 일치 하는 때마다 변경 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **인덱스** 속성입니다. 이 함수는 검색 문자열을 반복 하 고 인쇄는 **인덱스** 및 `lastIndex` 문자열에서 각 단어에 대 한 값입니다.  
  
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
      document.write (arr);  
      }  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [정규식 구문 (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)