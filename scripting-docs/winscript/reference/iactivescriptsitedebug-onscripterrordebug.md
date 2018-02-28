---
title: IActiveScriptSiteDebug::OnScriptErrorDebug | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptSiteDebug.OnScriptErrorDebug
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteDebug::OnScriptErrorDebug
ms.assetid: 87f201da-36eb-49a2-b000-e1e1e8c4cdb7
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3a669d435d84295b22af4298936babf8439eaefa
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsitedebugonscripterrordebug"></a>IActiveScriptSiteDebug::OnScriptErrorDebug
런타임 오류를 처리 하는 방법을 결정 하기 위해 스마트 호스트 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT OnScriptErrorDebug(  
   IActiveScriptErrorDebug*  pErrorDebug,  
   BOOL*                     pfEnterDebugger,  
   BOOL*                     pfCallOnScriptErrorWhenContinuing  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pErrorDebug`  
 [in] 발생 한 런타임 오류  
  
 `pfEnterDebugger`  
 [out] JIT 디버깅을 수행 하도록 디버거를 오류를 전달할지 여부를 나타내는 플래그입니다.  
  
 `pfCallOnScriptErrorWhenContinuing`  
 [out] 호출할지 여부를 나타내는 플래그 `IActiveScriptSite::OnScriptError` 디버깅 하지 않고 계속 하려면 사용자가 결정 하는 경우.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값은 포함 되지만 다음 해당에서 값으로 제한 되지 않습니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 스마트 호스트 런타임 오류를 처리 하는 방법을 결정 하기 위해이 메서드를 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptSiteDebug 인터페이스](../../winscript/reference/iactivescriptsitedebug-interface.md)