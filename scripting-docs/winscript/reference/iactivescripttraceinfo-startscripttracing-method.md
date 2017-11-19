---
title: "Iactivescripttraceinfo:: Startscripttracing 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 90fac5ed-ce15-49b7-a6f1-605ede6f34e2
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e999ad0d40f4d832330fee6db17b64ae9da50f08
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescripttraceinfostartscripttracing-method"></a>IActiveScriptTraceInfo::StartScriptTracing 메서드
스크립트 추적을 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT StartScriptTracing(     [in] IActiveScriptSiteTraceInfo * pSiteTraceInfo,     [in] GUID guidContextID );   
```  
  
#### <a name="parameters"></a>매개 변수  
 `pSiteTraceInfo`  
 호스트의 IActiveScriptSiteTraceInfo에 대 한 포인터입니다.  
  
 `guidContextId`  
 컨텍스트 GUID입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드에 대 한 가능한 반환 값은 다음과 같습니다.  
  
1.  S_OK: 성공 합니다.  
  
2.  E_POINTER: `pSiteTraceInfo` 는 NULL 포인터입니다.  
  
3.  E_NOTIMPL: 구현 되지 않았습니다.