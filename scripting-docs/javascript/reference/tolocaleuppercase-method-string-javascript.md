---
title: "toLocaleUpperCase 메서드 (String) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toLocaleUpperCase
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: toLocaleUpperCase method
ms.assetid: e927adb6-475e-44b2-91f7-cedda10a39b0
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 07a89560dde0319598da30fc3451524112b99eac
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="tolocaleuppercase-method-string-javascript"></a>toLocaleUpperCase 메서드(String)(JavaScript)
모든 영문자가 대문자로 변환 된 고려 호스트 환경의 현재 로캘의 된 하는 위치는 문자열을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
stringVar.toLocaleUpperCase( )  
```  
  
## <a name="remarks"></a>설명  
 필요한 `stringVar` 참조가 `String` 개체 또는 문자열 리터럴입니다.  
  
 `toLocaleUpperCase` 메서드 호스트 환경의 현재 로캘을 고려 하는 문자열의 문자를 변환 합니다. 대부분의 경우에서 결과 동일 결과로 `toUpperCase` 메서드. 결과는 언어에 대 한 규칙 일반 유니코드 대/소문자 매핑 충돌 하면 달라 집니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [문자열 개체](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [toLocaleLowerCase 메서드 (String)](../../javascript/reference/tolocalelowercase-method-string-javascript.md)   
 [toUpperCase 메서드(String)](../../javascript/reference/touppercase-method-string-javascript.md)