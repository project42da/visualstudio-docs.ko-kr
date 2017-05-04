---
title: "use strict 지시문 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "strict_JavaScriptKeyword"
  - "use strict"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "strict 모드"
  - "use strict 지시문"
  - "use strict"
ms.assetid: b532e8c9-548c-4bbe-b2fc-5459ebd62e56
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# use strict 지시문
JavaScript의 일부 기능 사용을 제한합니다.  Internet Explorer 10 및 [!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱에서만 지원됩니다.  
  
## 구문  
  
```javascript  
use strict  
```  
  
## 설명  
  
## 예제  
 다음 코드에서는 strict 모드에서 모든 변수가 `var`로 선언되어야 하기 때문에 구문 오류가 발생합니다.  
  
```javascript  
"use strict";  
function testFunction(){  
   var testvar = 4;  
    return testvar;  
}  
intvar = 5;  
  
```  
  
## 참고 항목  
 [strict 모드](../../javascript/advanced/strict-mode-javascript.md)