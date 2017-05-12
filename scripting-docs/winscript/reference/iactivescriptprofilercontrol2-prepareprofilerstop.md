---
title: "IActiveScriptProfilerControl2::PrepareProfilerStop | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScriptProfilerControl2::PrepareProfilerStop"
ms.assetid: e43a63bc-c44f-44a8-9db4-29062b9e6a16
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# IActiveScriptProfilerControl2::PrepareProfilerStop
해당 스크립팅 엔진에 프로 파일링을 중지 하려면 프로파일러에 알립니다.  이 메서드를 사용 하면 완전 한 호출 스택을 경우 얻을 수 있습니다 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 프로 파일링을 중지 하면 실행 됩니다.  
  
## 구문  
  
```  
HRESULT PrepareProfilerStop();  
```  
  
#### 매개 변수  
 메서드 매개 변수를 받지 않습니다.  
  
## 반환 값  
 HRESULT를 반환합니다.  다음과 같은 값을 사용할 수 있습니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_FAIL`|프로 파일링을 시작할 수 없습니다.|  
|`S_FALSE`|스크립트를 실행 하면 프로 파일링을 중지 했습니다.|  
|`ACTIVPROF_E_PROFILER_ABSENT`|프로 파일링을 사용할 수 없습니다.|  
  
## 설명  
 호출 `IActiveScriptProfilerControl2::PrepareProfilerStop` 이벤트에서 호출 스택의 함수에 대 한 전송 됩니다.  이 메서드는 현재 탭에서 모든 스크립트 엔진에는 프로 파일링을 중지 하기 전에 호출 해야 합니다.  모든 스크립팅 엔진에 대 한 메서드를 호출할 수 있습니다.  
  
## 참고 항목  
 [IActiveScriptProfilerControl2::CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md)   
 [IActiveScriptProfilerControl2 인터페이스](../../winscript/reference/iactivescriptprofilercontrol2-interface.md)