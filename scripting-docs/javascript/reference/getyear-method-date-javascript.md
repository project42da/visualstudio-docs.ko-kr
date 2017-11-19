---
title: "getYear 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getYear
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, returning year
- GetYear method
ms.assetid: 0e23e832-acd4-49a9-a175-515d0094f172
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a0e08fae8da1b102918de70650d09080a7ff7ebd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="getyear-method-date-javascript"></a>getYear 메서드(Date)(JavaScript)
연도 가져옵니다는 `Date` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.getYear()   
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 연도 반환 합니다.  
  
## <a name="remarks"></a>설명  
  
> [!IMPORTANT]
>  이 메서드는 더 이상에 대 한 이전 버전과 호환성을 위해서만 제공 됩니다. 대신 `getFullYear` 메서드를 사용합니다.  
  
 [!INCLUDE[jsv1textspecific](../../javascript/reference/includes/jsv1textspecific-md.md)], 한 다음 Internet Explorer 버전부터 [!INCLUDE[jsv9textspecific](../../javascript/reference/includes/jsv9textspecific-md.md)], 반환 값은 1900-저장된 된 연도입니다. 예를 들어 1899 년은-1을 반환 하 고 2000 년 새 해는 100으로 반환 됩니다.  
  
 [!INCLUDE[jsv3textspecific](../../javascript/reference/includes/jsv3textspecific-md.md)] 통해 [!INCLUDE[jsv58textspecific](../../javascript/reference/includes/jsv58textspecific-md.md)], 수식 연도에 따라 달라 집니다. 1900 년에서 1999 년에 대 한 반환 되는 값을 1900-저장된 년 2 자리 값이입니다. 범위를 벗어난 날짜에 대 한 4 자리 연도 반환 됩니다. 예를 들어, 96으로 1996 반환 되지만 1825 및 2025 그대로 반환 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getFullYear 메서드 (Date)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [getUTCFullYear 메서드 (Date)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [setFullYear 메서드 (Date)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setUTCFullYear 메서드 (Date)](../../javascript/reference/setutcfullyear-method-date-javascript.md)   
 [setYear 메서드(Date)](../../javascript/reference/setyear-method-date-javascript.md)