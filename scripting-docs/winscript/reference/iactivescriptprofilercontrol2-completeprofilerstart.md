---
title: "IActiveScriptProfilerControl2::CompleteProfilerStart | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScriptProfilerControl2::CompleteProfilerStart"
ms.assetid: e14d94a2-39d3-40a1-84d9-6300fbe2b339
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# IActiveScriptProfilerControl2::CompleteProfilerStart
적용 가능한 모든 스크립팅 엔진에서 프로 파일링 시작 된 프로파일러에 알립니다.  이 메서드를 사용 하면 완전 한 호출 스택을 경우 얻을 수 있습니다 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 프로 파일링을 시작할 때 실행 됩니다.  
  
## 구문  
  
```  
HRESULT CompleteProfilerStart();  
```  
  
#### 매개 변수  
 메서드 매개 변수를 받지 않습니다.  
  
## 반환 값  
 HRESULT를 반환합니다.  다음과 같은 값을 사용할 수 있습니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_FAIL`|프로 파일링을 시작할 수 없습니다.|  
|`S_FALSE`|스크립트를 실행 하면 프로 파일링을 시작 했습니다.|  
|`ACTIVPROF_E_PROFILER_ABSENT`|프로 파일링을 사용할 수 없습니다.  콜백 안 함으로 설정 되어 있습니다.|  
|`E_OUTOFMEMORY`|호출 스택에 메모리 부족 상태로 인해 얻을 수 없습니다.|  
  
## 설명  
 호출 `IActiveScriptProfilerControl2::CompleteProfilerStart` 이미 호출 스택에 있는 함수에 대 한 이벤트가 전송 됩니다.  이 메서드는 현재 탭에서 모든 스크립트 엔진에서 시작 프로 파일링 후 호출 해야 합니다.  모든 스크립팅 엔진에 대 한 메서드를 호출할 수 있습니다.  
  
## 참고 항목  
 [IActiveScriptProfilerControl2::PrepareProfilerStop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md)   
 [IActiveScriptProfilerControl2 인터페이스](../../winscript/reference/iactivescriptprofilercontrol2-interface.md)