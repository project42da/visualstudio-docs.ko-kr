---
title: "IActiveScriptProfilerCallback 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 76f9164b-b086-4b29-ac79-76f9c76f1d11
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f4dc4b9d4e3b1f83a37e64e3a85387fd378d3ca7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercallback-interface"></a>IActiveScriptProfilerCallback 인터페이스
이벤트가 발생할 때 프로파일러 개체에 알리기 위해 스크립팅 엔진에서 사용 되는 메서드를 제공 합니다. 이 인터페이스는 프로파일러 개체에 의해 구현 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IActiveScriptProfilerCallback::Initialize](../../winscript/reference/iactivescriptprofilercallback-initialize.md)|스크립팅 엔진에서 프로 파일링가 시작 될 때마다 프로파일러 개체를 초기화 하기 위해 호출 합니다.|  
|[IActiveScriptProfilerCallback::Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md)|해제 하 고 스크립팅 엔진에서 프로 파일링이 중지 될 때마다 프로파일러 개체를 해제 하기 위해 호출 합니다.|  
|[IActiveScriptProfilerCallback::ScriptCompiled](../../winscript/reference/iactivescriptprofilercallback-scriptcompiled.md)|개체의 스크립팅 엔진 하는 컴파일된 스크립트 프로파일러에 알립니다.|  
|[IActiveScriptProfilerCallback::FunctionCompiled](../../winscript/reference/iactivescriptprofilercallback-functioncompiled.md)|엔진의 스크립팅 개체는 스크립트를 컴파일하는 경우 함수에서 발생 했습니다 프로파일러에 알립니다.|  
|[IActiveScriptProfilerCallback::OnFunctionEnter](../../winscript/reference/iactivescriptprofilercallback-onfunctionenter.md)|스크립팅 엔진 문서 개체 모델 (DOM)에 대 한 호출 하지 않은 함수 호출을 실행 하려고 하는 프로파일러 개체를 알립니다.|  
|[IActiveScriptProfilerCallback::OnFunctionExit](../../winscript/reference/iactivescriptprofilercallback-onfunctionexit.md)|개체는 호출 하는 함수를 실행 하는 완료 된 스크립팅 엔진 아닌지 DOM에 대 한 호출 프로파일러에 알립니다.|  
  
## <a name="remarks"></a>설명  
 함수 호출 문서 개체 모델 (DOM)에 대 한 알림을에서 제공 되는 [IActiveScriptProfilerCallback2 인터페이스](../../winscript/reference/iactivescriptprofilercallback2-interface.md)합니다.  
  
> [!NOTE]
>  시작 하 고 스크립트를 실행 중일 때 프로 파일링을 중지 하는 기능을 추가 하려면 다음 메서드를 호출 합니다. 이러한 방법을 사용 하면 얻을 수 경우 완전 한 호출 스택이 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 시작 또는 프로 파일링을 중지 하는 경우를 실행 합니다.  
>   
>  -   호출 [IActiveScriptProfilerControl2::CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md) 프로파일러에 알립니다을 프로 파일링 시작 해야 합니다.  
> -   호출 [IActiveScriptProfilerControl2::PrepareProfilerStop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md) 프로파일러에 알립니다 프로 파일링를 중지 곧 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 프로파일러 인터페이스](../../winscript/reference/active-script-profiler-interfaces.md)