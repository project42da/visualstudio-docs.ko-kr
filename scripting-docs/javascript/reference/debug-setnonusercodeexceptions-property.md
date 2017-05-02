---
title: "Debug.setNonUserCodeExceptions 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 1dd2abee-a415-41bb-a359-017da62f9485
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# Debug.setNonUserCodeExceptions 속성
이 범위의 try\-catch 블록을 디버거에서 사용자가 처리하지 않음으로 처리할 것인지 여부를 결정합니다.  예외는 Throw됨, 사용자가 처리하지 않음 또는 처리되지 않음으로 분류할 수 있습니다.  
  
 속성이 주어진 범위에서 `true`로 설정되면 개발자가 사용자가 처리하지 않은 예외를 중단하도록 하려는 경우 디버거가 해당 범위 내에서 throw된 예외에 대해 조치\(예: 중단\)를 취할 것을 결정할 수 있습니다.  이 속성이 `false`로 설정되면 이 속성이 설정되지 않은 것과 같습니다.  
  
 디버깅에 대한 자세한 내용은 [활성 스크립트 디버깅 개요](http://go.microsoft.com/fwlink/p/?LinkId=249469)를 참조하세요.  
  
## 구문  
  
```  
Debug.setNonUserCodeExceptions [= bool];  
```  
  
## 예제  
 다음 코드에서는 이 속성을 설정하는 방법을 보여 줍니다.  
  
```javascript  
(function () {  
    Debug.setNonUserCodeExceptions = true;  
    try{  
        var x = null;  
        x.y();  
    } catch (e) {  
    // Catch the exception.  
    }  
})();  
```  
  
## 요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]