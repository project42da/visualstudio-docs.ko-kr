---
title: "toUpperCase 메서드 (String) (JavaScript) | Microsoft Docs"
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
- toUpperCase
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toUpperCase method
ms.assetid: 4fd4ccc3-e794-498a-9db1-baf48fc1dda1
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0b84de440fc9e3cece3b831b57a90be394e819ac
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="touppercase-method-string-javascript"></a>toUpperCase 메서드(String)(JavaScript)
문자열의 모든 알파벳 문자를 대문자로 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      strVariable.toUpperCase()  
"String Literal".toUpperCase()   
```  
  
## <a name="remarks"></a>설명  
 `toUpperCase` 메서드는-알파벳 이외의 문자에는 영향을 주지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는의 효과 `toUpperCase` 메서드:  
  
```JavaScript  
var str1 = "This is a STRING.";  
var str2 = str1.toUpperCase();  
document.write(str2);  
  
// Output: THIS IS A STRING.  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [문자열 개체](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [toLocaleUpperCase 메서드 (String)](../../javascript/reference/tolocaleuppercase-method-string-javascript.md)   
 [toLowerCase 메서드](../../javascript/reference/tolowercase-method-javascript.md)