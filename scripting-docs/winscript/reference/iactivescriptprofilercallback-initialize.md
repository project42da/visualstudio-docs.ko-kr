---
title: "IActiveScriptProfilerCallback::Initialize | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptProfilerCallback.Initialize
apilocation: scrobj.dll
ms.assetid: a257111e-a50b-4962-9dd6-c893d40f6985
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IActiveScriptProfilerCallback::Initialize
프로 파일링 스크립팅 엔진에서 시작 될 때마다 프로파일러 개체를 초기화 하기 위해 호출 됩니다.  
  
## 구문  
  
```  
HRESULT Initialize(  
    [in] DWORD dwContext);  
```  
  
#### 매개 변수  
 `dwContext`  
 \[in\] 전달 되는 4 바이트 값 [IActiveScriptProfilerControl::StartProfiling](../../winscript/reference/iactivescriptprofilercontrol-startprofiling.md).  
  
## 반환 값  
 HRESULT를 반환합니다.  다음과 같은 값을 사용할 수 있습니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 메서드는 프로파일러 개체를 초기화할 수 없습니다 경우 스크립팅 엔진에 알리기 위해 실패 HRESULT 반환 해야 합니다.  이 경우 스크립팅 엔진을 직접 호출할 수 [IActiveScriptProfilerCallback::Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md)HRESULT 매개 변수를 전달 하 고 다음 프로파일러 개체를 놓습니다.  
  
## 참고 항목  
 [IActiveScriptProfilerCallback 인터페이스](../../winscript/reference/iactivescriptprofilercallback-interface.md)