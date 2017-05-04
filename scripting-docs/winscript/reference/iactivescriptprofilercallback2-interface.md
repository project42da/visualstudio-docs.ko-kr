---
title: "IActiveScriptProfilerCallback2 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScriptProfilerCallback2 인터페이스"
ms.assetid: 8f2e62e4-c232-4dc3-a2c0-54dd06298306
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# IActiveScriptProfilerCallback2 인터페이스
스크립팅 엔진에서 프로파일러 개체 문서 개체 모델 \(DOM\) 이벤트가 발생할 때를 알리는 데 사용 되는 메서드를 제공 합니다.  이 인터페이스는 프로파일러 개체로 구현 됩니다.  
  
## 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md)|DOM 함수 호출을 실행 하려는 스크립트 프로파일러 개체를 알립니다.|  
|[IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md)|스크립트 엔진 개체 DOM 함수 호출이 실행 완료 프로파일러에 알립니다.|  
  
## 설명  
 `IActiveScriptProfilerCallback2` Internet Explorer 9 처음 발표 되는 인터페이스입니다.  
  
 Dom 호출 되지 않는 함수 호출의 알림을 제공 하는 것은 [IActiveScriptProfilerCallback 인터페이스](../../winscript/reference/iactivescriptprofilercallback-interface.md).  
  
> [!NOTE]
>  시작 스크립트를 실행 하면 프로 파일링을 중지 하는 기능을 추가 하려면 다음 메서드를 호출 합니다.  이 메서드를 사용 하면 완전 한 호출 스택을 경우 얻을 수 있습니다 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 시작 또는 프로 파일링을 중지 하는 경우 실행 됩니다.  
>   
>  -   호출 [IActiveScriptProfilerControl2::CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md) 프로 파일링 시작 된 프로파일러에 알릴 수 있습니다.  
> -   호출 [IActiveScriptProfilerControl2::PrepareProfilerStop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md) 프로파일러에 알리려면 곧 프로 파일링 중지 됩니다.  
  
## 참고 항목  
 [액티브 스크립트 프로파일러 인터페이스](../../winscript/reference/active-script-profiler-interfaces.md)