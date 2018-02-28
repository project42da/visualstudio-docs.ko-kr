---
title: "레이블이 문 (JavaScript) | Microsoft Docs"
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
- labeled_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- continue statement
- labeled statement
- identifiers, statements
ms.assetid: 019f898e-9e27-4be4-a22f-c5927c7fcae2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bd72b15d3fc9083ca127a48981c0cd0a7ee56b6c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="labeled-statement-javascript"></a>Labeled 문(JavaScript)
문의 식별자를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      label :  
   statements   
```  
  
## <a name="parameters"></a>매개 변수  
 *레이블*  
 필수 요소. Labeled 문을 지칭할 때 사용 하는 고유 식별자입니다.  
  
 `statements`  
 선택 사항입니다. 와 관련 된 하나 이상의 문을 *레이블*합니다.  
  
## <a name="remarks"></a>설명  
 레이블이 사용 되는 **나누기** 및 **계속** 있는 문을 지정 하는 문을 **나누기** 및 **계속** 적용 합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 **계속** 문이 참조는 **에 대 한** 앞에 오는 루프는 `Inner:` 문. 때 `j` 24는 **계속** 문을 사용 하면는 **에 대 한** 루프를 다음 반복으로 이동 합니다. 숫자 21-23과 25 30 사이의 각 줄에 인쇄 합니다.  
  
```JavaScript  
Outer:  
for (i = 1; i <= 10; i++) {  
   document.write ("<br />");  
   document.write ("i: " + i);  
   document.write (" j: ");  
  
Inner:  
   for (j = 21; j <= 30; j++) {  
      if (j == 24)  
          {  
          continue Inner;  
      }  
      document.write (j + " ");  
  }  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [break 문](../../javascript/reference/break-statement-javascript.md)   
 [continue 문](../../javascript/reference/continue-statement-javascript.md)