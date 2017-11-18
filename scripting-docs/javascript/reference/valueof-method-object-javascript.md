---
title: "valueOf 메서드 (Object) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: valueOf
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: valueOf method
ms.assetid: c555e38b-f451-4341-8fcd-4c8b02906a2c
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 677b56fd6fc142ce175b130d2f83291c1ac9535f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="valueof-method-object-javascript"></a>valueOf 메서드(Object)(JavaScript)
지정된 개체의 기본 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object.valueOf( )  
```  
  
## <a name="remarks"></a>설명  
 필요한 `object` 참조는 모든 내장 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체입니다.  
  
 `valueOf` 각각에 대해 메서드를 다르게 정의 내장 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체입니다.  
  
|개체|반환 값|  
|------------|------------------|  
|배열|배열 인스턴스를 반환합니다.|  
|부울|부울 값입니다.|  
|날짜|UTC 1970 년 1 월 1 일 자정 이후의 시간 (밀리초)에 저장 된 시간 값입니다.|  
|함수|자체는 함수입니다.|  
|수|숫자 값입니다.|  
|개체|개체 자체입니다. 이 값이 기본값입니다.|  
|문자열|문자열 값입니다.|  
  
 **수학** 및 `Error` 개체 하지 않은 한 `valueOf` 메서드.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
 **적용 대상**: [배열 개체](../../javascript/reference/array-object-javascript.md)&#124; [Boolean 개체](../../javascript/reference/boolean-object-javascript.md)&#124; [개체 날짜](../../javascript/reference/date-object-javascript.md)&#124; [개체 작동](../../javascript/reference/function-object-javascript.md)&#124; [개체 번호](../../javascript/reference/number-object-javascript.md)&#124; [개체 개체](../../javascript/reference/object-object-javascript.md)&#124; [문자열 개체](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [toString 메서드(Object)](../../javascript/reference/tostring-method-object-javascript.md)