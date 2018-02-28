---
title: IActiveScriptErrorDebug::GetDocumentContext | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptErrorDebug.GetDocumentContext
apilocation:
- jscript.dll
helpviewer_keywords:
- IActiveScriptErrorDebug::GetDocumentContext
ms.assetid: 567601a1-551a-4905-bda1-1f54610174f4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1342465ed306f43d07248f8e3c776e9e9af2c774
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescripterrordebuggetdocumentcontext"></a>IActiveScriptErrorDebug::GetDocumentContext
이 오류에 대 한 문서 컨텍스트를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetDocumentContext(  
   IDebugDocumentContext**  ppssc  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppssc`  
 [out] 이 오류에 대 한 문서 컨텍스트에서 가져왔습니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 문서 상황에 맞는 문자 위치 범위 오류에 해당 하는 모든 문자를 포함 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptErrorDebug 인터페이스](../../winscript/reference/iactivescripterrordebug-interface.md)