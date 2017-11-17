---
title: "toString 메서드 (Date) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: d3037289-d805-409b-8781-045c59a2c404
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 67b6dce74e3796c8b54431b56809473e3c5e59a5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="tostring-method-date"></a>toString 메서드(Date)
날짜의 문자열 표현을 반환합니다. 문자열의 형식은 로캘에 따라 다릅니다. 미국 영어 (en-미국)은 다음과 같습니다.  
  
 *요일* *월* *일* *시간*: *분*:*두 번째* *시간대* *연도*  
  
## <a name="syntax"></a>구문  
  
```  
  
date.toString()  
```  
  
## <a name="parameters"></a>매개 변수  
 `date`  
 필수 요소. 날짜를 문자열로 나타낼입니다.  
  
## <a name="return-value"></a>반환 값  
 날짜의 문자열 표현을 반환합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `toString` 날짜와 메서드.  
  
```JavaScript  
var myDate = new Date();  
myDate.setFullYear(2100, 5, 5);  
var dateString = myDate.toString();  
document.write(dateString);  
  
// Output: <date>  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]