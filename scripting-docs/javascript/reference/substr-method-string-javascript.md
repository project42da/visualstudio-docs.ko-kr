---
title: "substr 메서드 (String) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: substr
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: substr method
ms.assetid: f12541c1-2623-482e-941d-2e22bc3c4a4a
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6b002bfefbeb81c534c882fa4a4720c93ccca185
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="substr-method-string-javascript"></a>substr 메서드(String)(JavaScript)
지정된 된 위치에서 시작 하 고 지정 된 길이가 부분 문자열을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
stringvar.substr(start [, length ])   
```  
  
## <a name="parameters"></a>매개 변수  
 `stringvar`  
 필수 요소. 문자열 리터럴 또는 `String` 부분 문자열을 추출할 개체입니다.  
  
 `start`  
 필수 요소. 원하는 부분 문자열의 시작 위치입니다. 문자열의 첫 번째 문자의 인덱스는 0입니다.  
  
 `length`  
 선택 사항입니다. 반환된 된 부분 문자열에 포함할 문자의 수입니다.  
  
## <a name="remarks"></a>설명  
 경우 `length` 가 0 또는 음수 이면 빈 문자열이 반환 됩니다. 부분 문자열의 끝으로 계속 지정 하지 않으면 `stringvar`합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `substr` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var s = "The quick brown fox jumps over the lazy dog.";  
var ss = s.substr(10, 5);    
document.write("[" + ss + "] <br>");  
  
ss = s.substr(10);  
document.write("[" + ss + "] <br>");  
  
ss = s.substr(10, -5);  
document.write("[" + ss + "] <br>");  
  
// Output:  
// [brown]   
// [brown fox jumps over the lazy dog.]   
// []  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [문자열 개체](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [substring 메서드(String)](../../javascript/reference/substring-method-string-javascript.md)