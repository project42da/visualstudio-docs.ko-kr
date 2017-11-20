---
title: "use strict 지시문 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- strict_JavaScriptKeyword
- use strict
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- strict mode
- use strict directive
- use strict
ms.assetid: b532e8c9-548c-4bbe-b2fc-5459ebd62e56
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0bd951255f5d5719c3aa216965605840ba12010d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="use-strict-directive"></a>use strict 지시문
JavaScript에서 일부 기능의 사용을 제한 합니다. Internet Explorer 10에서에서 지원 및 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱만 해당 합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
use strict  
```  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예제  
 Strict 모드에서는 모든 변수를 선언 해야 하기 때문에 다음 코드에서 구문 오류를 발생 `var`합니다.  
  
```JavaScript  
"use strict";  
function testFunction(){  
   var testvar = 4;  
    return testvar;  
}  
intvar = 5;  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [Strict Mode](../../javascript/advanced/strict-mode-javascript.md)