---
title: IActiveScriptSiteDebugEx::OnCanNotJITScriptErrorDebug | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptSiteDebugEx.OnCanNotJITScriptErrorDebug
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteDebugEx::OnCanNotJITScriptErrorDebug
ms.assetid: 83f81476-bf12-47f2-897d-1d37d21137d4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e428f12b3d199603ac341a5e069fcc5ce5d36f93
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsitedebugexoncannotjitscripterrordebug"></a>IActiveScriptSiteDebugEx::OnCanNotJITScriptErrorDebug
프로세스 관리자를 디버그할 때 스크립트 런타임 오류에 대 한 호스트 Just In Time 스크립트 디버거를 찾지 못하면에 알립니다.  
  
 처리 해야 호스트에서 디버거를 구현 하려면 [IActiveScriptSiteDebug::OnScriptErrorDebug](../../winscript/reference/iactivescriptsitedebug-onscripterrordebug.md)합니다. 사용자 작업에 따라, 호스트 하거나 디버거를 연결할 수 고를 반환 하거나, 디버거는 OnScriptErrorDebug에서 시작 하는 반환 `pfEnterDebugger` 매개 변수입니다. 또한 프로세스 디버깅 관리자에 의해 해석 될 수 있는 외부 디버거 없는 경우에 런타임 오류에 대 한 알림을 가져올이 인터페이스를 구현 해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT OnCanNotJITScriptErrorDebug(  
   IActiveScriptErrorDebug*  pErrorDebug  
   BOOL *pfCallOnScriptErrorWhenContinuing  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pErrorDebug`  
 [in] 런타임 오류가 발생 한 경우  
  
 `pfCallOnScriptErrorWhenContinuingt`  
 [out] 호출할지 여부를 [IActiveScriptSiteDebug::OnScriptErrorDebug](../../winscript/reference/iactivescriptsitedebug-onscripterrordebug.md) 디버깅 하지 않고 계속 하려면 사용자가 결정 합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 알림이를 구현 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptSiteDebugEx 인터페이스](../../winscript/reference/iactivescriptsitedebugex-interface.md)