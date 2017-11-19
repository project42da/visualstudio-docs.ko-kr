---
title: "IActiveScriptProfilerCallback2 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IActiveScriptProfilerCallback2 interface
ms.assetid: 8f2e62e4-c232-4dc3-a2c0-54dd06298306
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2dc9fcd8ca4afec0fb474c0f3a7317b608c7c9f6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercallback2-interface"></a>IActiveScriptProfilerCallback2 인터페이스
문서 개체 모델 (DOM) 이벤트가 발생할 때 프로파일러 개체에 알리기 위해 스크립팅 엔진에서 사용 되는 메서드를 제공 합니다. 이 인터페이스는 프로파일러 개체에 의해 구현 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md)|스크립팅 엔진 DOM 함수 호출을 실행 하려고 합니다. 프로파일러 개체를 알립니다.|  
|[IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md)|엔진의 스크립팅 개체는 DOM 함수 호출 실행을 완료 프로파일러에 알립니다.|  
  
## <a name="remarks"></a>설명  
 `IActiveScriptProfilerCallback2` Internet Explorer 9와 함께 처음 릴리스 하는 인터페이스입니다.  
  
 DOM으로 호출 하지 않은 함수 호출에 대 한 알림을에서 제공 되는 [IActiveScriptProfilerCallback 인터페이스](../../winscript/reference/iactivescriptprofilercallback-interface.md)합니다.  
  
> [!NOTE]
>  시작 하 고 스크립트를 실행 중일 때 프로 파일링을 중지 하는 기능을 추가 하려면 다음 메서드를 호출 합니다. 이러한 방법을 사용 하면 얻을 수 경우 완전 한 호출 스택이 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 시작 또는 프로 파일링을 중지 하는 경우를 실행 합니다.  
>   
>  -   호출 [IActiveScriptProfilerControl2::CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md) 프로파일러에 알립니다을 프로 파일링 시작 해야 합니다.  
> -   호출 [IActiveScriptProfilerControl2::PrepareProfilerStop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md) 프로파일러에 알립니다 프로 파일링를 중지 곧 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 프로파일러 인터페이스](../../winscript/reference/active-script-profiler-interfaces.md)