---
title: "ScriptEngine 함수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: ScriptEngine
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: ScriptEngine function
ms.assetid: 65674b2b-d2c2-4493-99b3-f0d20fda8249
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d441fcce065677f7b673a9979acff9cf9aa2ce90
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="scriptengine-function-javascript"></a>ScriptEngine 함수(JavaScript)
사용 중인 스크립트 언어의 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
ScriptEngine()  
```  
  
## <a name="remarks"></a>설명  
 `ScriptEngine` 함수는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]가 현재 스크립팅 엔진임을 나타내는 "JScript"를 반환합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `ScriptEngine` 함수를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
if (window.ScriptEngine) {  
    console.log(window.ScriptEngine());  
}  
  
// Output: JScript  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ScriptEngineBuildVersion 함수](../../javascript/reference/scriptenginebuildversion-function-javascript.md)   
 [ScriptEngineMajorVersion 함수](../../javascript/reference/scriptenginemajorversion-function-javascript.md)   
 [ScriptEngineMinorVersion 함수](../../javascript/reference/scriptengineminorversion-function-javascript.md)