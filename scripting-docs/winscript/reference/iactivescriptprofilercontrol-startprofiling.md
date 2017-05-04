---
title: "IActiveScriptProfilerControl::StartProfiling | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptProfilerControl.StartProfiling
apilocation: scrobj.dll
ms.assetid: 56a7b3b7-8c21-43d0-9d8b-53bbc19fabb9
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptProfilerControl::StartProfiling
스크립팅 엔진의 프로 파일링을 시작 합니다.  스크립팅 엔진에 호출 하 여 프로파일러 개체의 인스턴스를 만듭니다 [CoCreateInstance](http://msdn.microsoft.com/ko-kr/7295a55b-12c7-4ed0-a7a4-9ecee16afdec).  
  
## 구문  
  
```  
HRESULT StartProfiling(  
    [in] REFCLSID clsidProfilerObject,  
    [in] DWORD dwEventMask,  
    [in] DWORD dwContext);  
```  
  
#### 매개 변수  
 `clsidProfilerObject`  
 \[in\] 클래스 식별자 \(CLSID\) 프로파일러 개체를 만들 수의.  
  
 `dwEventMask`  
 \[in\] 이벤트 유형을 지정 하는 4 바이트 비트 마스크입니다.  비트에 정의 된 [PROFILER\_EVENT\_MASK 열거형](../../winscript/reference/profiler-event-mask-enumeration.md).  
  
 `dwContext`  
 \[in\] 프로파일러에 개체를 전달 하는 4 바이트 값입니다.  
  
## 반환 값  
 HRESULT를 반환합니다.  다음과 같은 값을 사용할 수 있습니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`ACTIVPROF_E_PROFILER_PRESENT`|이미 프로 파일링 활성화 됩니다.|  
  
## 참고 항목  
 [IActiveScriptProfilerControl 인터페이스](../../winscript/reference/iactivescriptprofilercontrol-interface.md)