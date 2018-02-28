---
title: "ScriptEngineBuildVersion 함수 (JavaScript) | Microsoft Docs"
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
- ScriptEngineBuildVersion
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- ScriptEngineBuildVersion function
ms.assetid: 7e255030-b0a3-420b-9c96-bb3e93c9333f
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fd458d43bebfb0d0e0b2cb6bebb483c22a60b4f0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="scriptenginebuildversion-function-javascript"></a>ScriptEngineBuildVersion 함수(JavaScript)
사용 중인 스크립팅 엔진의 빌드 버전 번호를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
ScriptEngineBuildVersion()  
```  
  
## <a name="remarks"></a>설명  
 반환 값은 사용 중인 스크립트 언어에 대한 DLL(동적 연결 라이브러리)에 포함된 버전 정보에 직접 해당합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `ScriptEngineBuildVersion` 함수를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
if(window.ScriptEngineBuildVersion) {  
    console.log(window.ScriptEngineBuildVersion());  
}  
  
// Output: <current build version>  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ScriptEngine 함수](../../javascript/reference/scriptengine-function-javascript.md)   
 [ScriptEngineMajorVersion 함수](../../javascript/reference/scriptenginemajorversion-function-javascript.md)   
 [ScriptEngineMinorVersion 함수](../../javascript/reference/scriptengineminorversion-function-javascript.md)