---
title: "Debug.setNonUserCodeExceptions 속성 | Microsoft Docs"
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
ms.assetid: 1dd2abee-a415-41bb-a359-017da62f9485
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3f53084d5580bc7b6b6c6356268dc60f519b2bd6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="debugsetnonusercodeexceptions-property"></a>Debug.setNonUserCodeExceptions 속성
이 범위에 있는 모든 try / catch 블록으로 사용자가 처리 디버거에 의해 처리 되는지 여부를 결정 합니다. 예외 throw 사용자가 처리 하는 것으로 분류 또는 처리 되지 않은 수 있습니다.  
  
 이 속성 설정 되어 있으면 `true` 정해진된 범위에서 디버거 그러면 확인할 수 있습니다 (예를 들어 중단) 작업을 수행 하는 개발자가 사용자가 처리 하지 않은 예외에서 중단 하려는 경우 해당 범위 내에서 throw 된 예외에 대. 이 속성이 `false` 속성이 설정 되지 않았으면 하는 경우에 동일 합니다.  
  
 디버깅에 대 한 자세한 내용은 참조 하십시오. [액티브 스크립트 디버깅 개요](http://go.microsoft.com/fwlink/p/?LinkId=249469)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Debug.setNonUserCodeExceptions [= bool];  
```  
  
## <a name="example"></a>예제  
 다음 코드에서는 이 속성을 설정하는 방법을 보여 줍니다.  
  
```JavaScript  
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
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]