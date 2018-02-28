---
title: "toLowerCase 메서드 (JavaScript) | Microsoft Docs"
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
- toLowerCase
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toLowerCase method
ms.assetid: dfd543b9-3e7a-4f83-a391-9cde109ad6bc
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b7510e074c11cf3d3f63b965bcd6f14946dc5a16
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="tolowercase-method-javascript"></a>toLowerCase 메서드(JavaScript)
문자열의 모든 알파벳 문자를 소문자로 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      strVariable.toLowerCase()  
"String Literal".toLowerCase()   
```  
  
## <a name="remarks"></a>설명  
 `toLowerCase` 메서드는-알파벳 이외의 문자에는 영향을 주지 않습니다.  
  
 다음 예제에서는의 효과 `toLowerCase` 메서드:  
  
```JavaScript  
var str1 = "This is a STRING.";  
var str2 = str1. toLowerCase();  
document.write(str2);  
  
// Output: this is a string.  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [문자열 개체](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [toLocaleLowerCase 메서드 (String)](../../javascript/reference/tolocalelowercase-method-string-javascript.md)   
 [toUpperCase 메서드(String)](../../javascript/reference/touppercase-method-string-javascript.md)