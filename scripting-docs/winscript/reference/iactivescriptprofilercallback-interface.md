---
title: "IActiveScriptProfilerCallback 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 76f9164b-b086-4b29-ac79-76f9c76f1d11
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# IActiveScriptProfilerCallback 인터페이스
스크립팅 엔진에서 이벤트가 발생할 때 프로파일러 개체에 알리기 위해 사용 되는 메서드를 제공 합니다.  이 인터페이스는 프로파일러 개체로 구현 됩니다.  
  
## 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IActiveScriptProfilerCallback::Initialize](../../winscript/reference/iactivescriptprofilercallback-initialize.md)|프로 파일링 스크립팅 엔진에서 시작 될 때마다 프로파일러 개체를 초기화 하기 위해 호출 됩니다.|  
|[IActiveScriptProfilerCallback::Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md)|호출 확보 한 프로 파일링 스크립팅 엔진이 중지 될 때마다 프로파일러 개체를 해제 합니다.|  
|[IActiveScriptProfilerCallback::ScriptCompiled](../../winscript/reference/iactivescriptprofilercallback-scriptcompiled.md)|스크립트 개체는 스크립트 엔진 컴파일 프로파일러에 알립니다.|  
|[IActiveScriptProfilerCallback::FunctionCompiled](../../winscript/reference/iactivescriptprofilercallback-functioncompiled.md)|스크립트를 컴파일하는 경우 함수 개체는 스크립팅 엔진을 발생 프로파일러에 알립니다.|  
|[IActiveScriptProfilerCallback::OnFunctionEnter](../../winscript/reference/iactivescriptprofilercallback-onfunctionenter.md)|프로파일러 개체를 스크립팅 엔진 문서 개체 모델 \(DOM\)에 대 한 호출 되지 않는 함수 호출을 실행 하는 것을 알립니다.|  
|[IActiveScriptProfilerCallback::OnFunctionExit](../../winscript/reference/iactivescriptprofilercallback-onfunctionexit.md)|함수 실행이 완료 된 스크립팅 엔진을 호출 하는 개체는 DOM 호출 아닙니다 프로파일러에 알립니다.|  
  
## 설명  
 알림 함수 호출에는 DOM \(문서 개체 모델\)을 제공 하는 것은 [IActiveScriptProfilerCallback2 인터페이스](../../winscript/reference/iactivescriptprofilercallback2-interface.md).  
  
> [!NOTE]
>  시작 스크립트를 실행 하면 프로 파일링을 중지 하는 기능을 추가 하려면 다음 메서드를 호출 합니다.  이 메서드를 사용 하면 완전 한 호출 스택을 경우 얻을 수 있습니다 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 시작 또는 프로 파일링을 중지 하는 경우 실행 됩니다.  
>   
>  -   호출 [IActiveScriptProfilerControl2::CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md) 프로 파일링 시작 된 프로파일러에 알릴 수 있습니다.  
> -   호출 [IActiveScriptProfilerControl2::PrepareProfilerStop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md) 프로파일러에 알리려면 곧 프로 파일링 중지 됩니다.  
  
## 참고 항목  
 [액티브 스크립트 프로파일러 인터페이스](../../winscript/reference/active-script-profiler-interfaces.md)