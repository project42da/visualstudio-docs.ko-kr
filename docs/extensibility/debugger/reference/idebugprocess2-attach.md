---
title: "IDebugProcess2::Attach | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProcess2::Attach"
helpviewer_keywords: 
  - "IDebugProcess2::Attach"
ms.assetid: 40d78417-fde2-45c3-96c9-16e06bd9008d
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProcess2::Attach
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

세션 디버그 매니저 \(SDM\)은 프로세스에 연결 합니다.  
  
## 구문  
  
```cpp#  
HRESULT Attach(   
   IDebugEventCallback2* pCallback,  
   GUID*                 rgguidSpecificEngines,  
   DWORD                 celtSpecificEngines,  
   HRESULT*              rghrEngineAttach  
);  
```  
  
```c#  
int Attach(   
   IDebugEventCallback2 pCallback,  
   Guid[]               rgguidSpecificEngines,  
   uint                 celtSpecificEngines,  
   int[]                rghrEngineAttach  
);  
```  
  
#### 매개 변수  
 `pCallback`  
 \[in\] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 사용에 대 한 디버그 이벤트 알림을 개체.  
  
 `rgguidSpecificEngines`  
 \[in\] 프로세스에서 실행 중인 프로그램을 디버깅 하는 데 디버그 엔진의 Guid의 배열입니다.  이 매개 변수는 null 값입니다.  에 대 한 자세한 내용은 설명 부분을 참조 하십시오.  
  
 `celtSpecificEngines`  
 \[in\] 디버그 빠르게에 `rgguidSpecificEngines` 배열 및 크기는 `rghrEngineAttach` 배열입니다.  
  
 `rghrEngineAttach`  
 \[in, out\] 디버그 엔진에서 반환 된 HRESULT 코드의 배열입니다.  이 배열의 크기를 지정 된는 `celtSpecificEngines` 매개 변수.  각 코드 일반적입니다 `S_OK` 또는 `S_ATTACH_DEFERRED`.  후자는 DE 없는 프로그램에 현재 연결 된 나타냅니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  다른 가능한 값은 다음과 같습니다.  
  
|값|설명|  
|-------|--------|  
|`E_ATTACH_DEBUGGER_ALREADY_ATTACHED`|지정 된 프로세스에 디버거가 이미 연결 되어.|  
|`E_ATTACH_DEBUGGEE_PROCESS_SECURITY_VIOLATION`|보안 위반이 연결 과정 동안 발생 했습니다.|  
|`E_ATTACH_CANNOT_ATTACH_TO_DESKTOP`|데스크톱 프로세스에 디버거를 첨부할 수 없습니다.|  
  
## 설명  
 프로세스에 연결 하는 SDM 지정 된 디버깅 엔진 \(DE\)에서 디버깅할 수 있는 프로세스에서 실행 중인 모든 프로그램에 연결 되어 있는 `rgguidSpecificEngines` 배열입니다.  설정는 `rgguidSpecificEngines` 매개 변수는 null 값을 포함 하거나 포함 `GUID_NULL` 배열의 모든 프로그램의 프로세스에서를 연결 합니다.  
  
 프로세스에서 발생 하는 모든 디버그 이벤트가 전송 되는 주어진 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 개체입니다.  이 `IDebugEventCallback2` 개체는 SDM이이 메서드를 호출할 때 제공 됩니다.  
  
## 참고 항목  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)