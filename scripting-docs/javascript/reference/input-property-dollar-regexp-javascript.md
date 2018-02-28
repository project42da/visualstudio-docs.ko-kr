---
title: "input 속성 ($_) (RegExp) (JavaScript) | Microsoft Docs"
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
- $_
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- input property
- $_ property
ms.assetid: 88c6d1d8-56f7-4334-a7eb-e899aec9cda4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8a447950783473d975bfe799eaa2bf18008e539e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="input-property--regexp-javascript"></a>input 속성($_)(RegExp)(JavaScript)
정규식 검색에 문자열을 반환 합니다. 읽기 전용입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
RegExp.input  
```  
  
## <a name="remarks"></a>설명  
 이 속성에 연결 된 개체는 항상 전역 `RegExp` 개체입니다.  
  
 값 **입력** 속성은 검색 된 문자열이 변경 될 때마다 수정 됩니다.  
  
 다음 예제에서는 **입력** 속성:  
  
```JavaScript  
function inputDemo(){  
   var s;  
   var re = new RegExp("d(b+)(d)","ig");  
   var str = "cdbBdbsbdbdz";  
   var arr = re.exec(str);  
   s = "The string used for the match was " + RegExp.input;   
   return(s);  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [정규식 구문 (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)