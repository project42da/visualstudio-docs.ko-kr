---
title: "toLocaleLowerCase 메서드 (String) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toLocaleLowerCase
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: toLocaleLowerCase method
ms.assetid: add894d3-d14a-4dbc-a9b9-7ad1d3a2e581
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 642ced387e0d3b4cf763767ec147d6160ed7d36b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="tolocalelowercase-method-string-javascript"></a>toLocaleLowerCase 메서드(String)(JavaScript)
호스트 환경의 현재 로캘을 고려 하는 모든 알파벳 문자를 소문자로 변환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
stringVar.toLocaleLowerCase( )  
```  
  
## <a name="remarks"></a>설명  
 필요한 `stringVar` 참조가 `String` 개체 또는 문자열 리터럴입니다.  
  
 `toLocaleLowerCase` 메서드 호스트 환경의 현재 로캘을 고려 하는 문자열의 문자를 변환 합니다. 대부분의 경우에서 결과 동일의 결과로 `toLowerCase` 메서드. 결과는 언어에 대 한 규칙 일반 유니코드 대/소문자 매핑 충돌 하면 달라 집니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [문자열 개체](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [toLocaleUpperCase 메서드 (String)](../../javascript/reference/tolocaleuppercase-method-string-javascript.md)   
 [toLowerCase 메서드](../../javascript/reference/tolowercase-method-javascript.md)