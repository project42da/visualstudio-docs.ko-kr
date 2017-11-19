---
title: "Date.now 함수 (JavaScript) | Microsoft Docs"
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
helpviewer_keywords: now method
ms.assetid: 41beda89-1a40-4fb1-88b0-38c090af739b
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 41a098c55b8ced3c630d3724615835301b6f00c8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="datenow-function-javascript"></a>Date.now 함수(JavaScript)
현재 날짜 및 시간을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Date.now()  
```  
  
## <a name="return-value"></a>반환 값  
 1970 년 1 월 1 일 자정 현재 날짜 및 시간 사이의 밀리초 수입니다.  
  
## <a name="remarks"></a>설명  
 [getTime 메서드](../../javascript/reference/gettime-method-date-javascript.md) 사이의 밀리초 수를 반환 하 고 지정된 된 날짜 1970 년 1 월 1 일입니다.  
  
 날짜 비교 및 경과 시간을 계산 하는 방법에 대 한 정보를 참조 하십시오. [시간과 날짜를 계산 (JavaScript)](../../javascript/calculating-dates-and-times-javascript.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `now` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var start = Date.now();  
var response = prompt("What is your name?", "");  
var end = Date.now();  
var elapsed = (end - start) / 1000;  
document.write("You took " + elapsed + " seconds" + " to type: " + response);  
  
// Output:  
// You took <seconds> seconds to type: <name>  
```  
  
## <a name="requirements"></a>요구 사항  
 지원된 되지 않는 설치 된 이전 버전의 Internet Explorer 9입니다. 그러나 다음과 같은 문서 모드에서 지원 됩니다: Quirks, Internet Explorer 6 표준, Internet Explorer 7 표준, Internet Explorer 8 표준, Internet Explorer 9 표준, Internet Explorer 10 표준. 에서도 지원 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱.  
  
## <a name="see-also"></a>참고 항목  
 [getTime 메서드 (Date)](../../javascript/reference/gettime-method-date-javascript.md)   
 [Date 개체](../../javascript/reference/date-object-javascript.md)   
 [날짜 및 시간 계산 (JavaScript)](../../javascript/calculating-dates-and-times-javascript.md)   
 [JavaScript 메서드](../../javascript/reference/javascript-methods.md)