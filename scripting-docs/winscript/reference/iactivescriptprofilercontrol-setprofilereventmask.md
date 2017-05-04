---
title: "IActiveScriptProfilerControl::SetProfilerEventMask | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptProfilerControl.SetProfilerEventMask
apilocation: scrobj.dll
ms.assetid: 207e192f-e12e-4fcb-b4d8-eaee50ecb86e
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptProfilerControl::SetProfilerEventMask
스크립팅 엔진을 발생 해야 하는 이벤트 유형을 지정 하는 4 바이트 비트 마스크를 설정 합니다.  
  
## 구문  
  
```  
RESULT SetProfilerEventMask(  
    [in] DWORD dwEventMask);  
```  
  
#### 매개 변수  
 `dwEventMask`  
 \[in\] 이벤트 유형을 지정 하는 4 바이트 비트 마스크입니다.  비트에 정의 된 [PROFILER\_EVENT\_MASK 열거형](../../winscript/reference/profiler-event-mask-enumeration.md).  
  
## 반환 값  
 HRESULT를 반환합니다.  다음과 같은 값을 사용할 수 있습니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`ACTIVPROF_E_PROFILER_ABSENT`|프로 파일링을 사용할 수 없습니다.|  
  
## 참고 항목  
 [IActiveScriptProfilerControl 인터페이스](../../winscript/reference/iactivescriptprofilercontrol-interface.md)