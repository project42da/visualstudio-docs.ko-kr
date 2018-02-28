---
title: "setYear 메서드 (Date) (JavaScript) | Microsoft Docs"
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
- setYear
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Year method
- setYear method
ms.assetid: 36431050-e0ec-45ee-830d-0d7c20e207ea
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5a9318de4a9420e0518dcd7f00a51c7161a8f92c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="setyear-method-date-javascript"></a>setYear 메서드(Date)(JavaScript)
연도 값을 설정 합니다.는 `Date` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.setYear(numYear)   
```  
  
## <a name="parameters"></a>매개 변수  
 `dateObj`  
 필수 요소. 모든 `Date` 개체입니다.  
  
 `numYear`  
 필수 요소. 부터 1999 1900 년 이것이 뺀 1900 년에는 숫자 값입니다. 범위를 벗어난 날짜에 대 한 4 자리 숫자 값입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 더 이상 유지 관리 됩니다에 대 한 이전 버전과 호환성을 위해서만 합니다. 대신 `setFullYear` 메서드를 사용합니다.  
  
 연도 설정 하는 `Date` 1997 년 개체 호출 **setyear (97)**합니다. 2010 년을 설정 하려면 호출 **setYear(2010)**합니다. 마지막으로, 연도 범위는 0-99의 연도 설정 하려면 사용 된 `setFullYear` 메서드.  
  
> [!NOTE]
>  에 대 한 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 버전 1.0에서 `setYear` 결과인 제공한 연도 값에 1900을 추가 하는 값을 사용 하 여 `numYear`year 값에 관계 없이 합니다. 예를 들어, 1899 년을 설정 하려면 `numYear` 은-1 2000 년을 설정 하 고 `numYear` 은 100입니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getFullYear 메서드 (Date)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [getUTCFullYear 메서드 (Date)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [getYear 메서드 (Date)](../../javascript/reference/getyear-method-date-javascript.md)   
 [setFullYear 메서드 (Date)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setUTCFullYear 메서드(Date)](../../javascript/reference/setutcfullyear-method-date-javascript.md)