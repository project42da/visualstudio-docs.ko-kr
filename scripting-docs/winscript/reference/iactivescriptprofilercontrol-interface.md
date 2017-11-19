---
title: "IActiveScriptProfilerControl 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 1448b394-9743-41b5-8eb9-5026a45773a4
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f0d598302ae78ca0b2a1e7c1f94c949800378a2e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercontrol-interface"></a>IActiveScriptProfilerControl 인터페이스
프로 파일링 지 스크립팅 엔진에 의해 구현 됩니다. 일반적으로 구현 하는 개체는 `IActiveScriptProfilerControl` 도 구현 하는 [IActiveScript](../../winscript/reference/iactivescript.md) 인터페이스입니다. 이 경우에 대 한 핸들을 가져올 수 있습니다는 `IActiveScriptProfilerControl` 호출 하 여 인터페이스는 `IUnknown::QueryInterface` 개체에서 메서드. 인터페이스를 중지 하 고 스크립팅 엔진에서 프로 파일링 시작에 필요한 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IActiveScriptProfilerControl::StartProfiling](../../winscript/reference/iactivescriptprofilercontrol-startprofiling.md)|스크립팅 엔진에서 프로 파일링을 시작 합니다.|  
|[IActiveScriptProfilerControl::SetProfilerEventMask](../../winscript/reference/iactivescriptprofilercontrol-setprofilereventmask.md)|스크립팅 엔진에서 프로파일러 이벤트 마스크를 설정합니다.|  
|[IActiveScriptProfilerControl::StopProfiling](../../winscript/reference/iactivescriptprofilercontrol-stopprofiling.md)|스크립팅 엔진에서 프로 파일링을 중지 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 프로파일러 인터페이스](../../winscript/reference/active-script-profiler-interfaces.md)