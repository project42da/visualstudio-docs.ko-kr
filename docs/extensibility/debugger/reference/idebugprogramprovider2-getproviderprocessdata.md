---
title: "IDebugProgramProvider2::GetProviderProcessData | Microsoft Docs"
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
  - "IDebugProgramProvider2::GetProviderProcessData"
helpviewer_keywords: 
  - "IDebugProgramProvider2::GetProviderProcessData"
ms.assetid: 90cf7b7f-53d2-487e-b793-94501a6e24dd
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgramProvider2::GetProviderProcessData
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

지정 된 프로세스에서 실행 중인 프로그램의 목록을 검색 합니다.  
  
## 구문  
  
```cpp  
HRESULT GetProviderProcessData(  
   PROVIDER_FLAGS         Flags,  
   IDebugDefaultPort2*    pPort,  
   AD_PROCESS_ID          processId,  
   CONST_GUID_ARRAY       EngineFilter,  
   PROVIDER_PROCESS_DATA* pProcess  
);  
```  
  
```c#  
int GetProviderProcessData(  
   enum_PROVIDER_FLAGS     Flags,  
   IDebugDefaultPort2      pPort,  
   AD_PROCESS_ID           ProcessId,  
   CONST_GUID_ARRAY        EngineFilter,  
   PROVIDER_PROCESS_DATA[] pProcess  
);  
```  
  
#### 매개 변수  
 `Flags`  
 \[in\] 플래그의 조합에서 [PROVIDER\_FLAGS](../../../extensibility/debugger/reference/provider-flags.md) 열거형입니다.  다음 플래그는이 호출에 대 한 일반적인 있습니다.  
  
|플래그|설명|  
|---------|--------|  
|`PFLAG_REMOTE_PORT`|호출자가 원격 컴퓨터에서 실행 중입니다.|  
|`PFLAG_DEBUGGEE`|호출자를 현재 디버깅 되 고 있습니다 \(마샬링 정보 반환 됩니다 각 노드에 대 한\).|  
|`PFLAG_ATTACHED_TO_DEBUGGEE`|호출자가 연결 하지만 여 디버거를 시작할 수 없습니다.|  
|`PFLAG_GET_PROGRAM_NODES`|호출자에 게 반환할 프로그램 노드 목록에 대 한 요청.|  
  
 `pPort`  
 \[in\] 호출 프로세스가 포트에서 실행 됩니다.  
  
 `processId`  
 \[in\] [AD\_PROCESS\_ID](../../../extensibility/debugger/reference/ad-process-id.md) 구조를 프로그램에 포함 되어 있는 프로세스의 ID를 보유 합니다.  
  
 `EngineFilter`  
 \[in\] Guid의 배열을 할당 \(이 어떤 주어진된 엔진 지원; 기반으로 실제로 반환 되는 프로그램을 필터링 하는 데 사용 됩니다이 프로세스를 디버깅 하려면 디버깅 엔진에 대 한 엔진이 지정 된 경우 다음 모든 프로그램 반환 됩니다\).  
  
 `pProcess`  
 \[out\] A [PROVIDER\_PROCESS\_DATA](../../../extensibility/debugger/reference/provider-process-data.md) 구조 요청 된 정보로 채워집니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 정상적으로이 메서드를 호출 하 여 해당 프로세스에서 실행 중인 프로그램의 목록을 얻을 수 있는 프로세스.  반환 된 정보를 목록입니다 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 개체입니다.  
  
## 참고 항목  
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)   
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [AD\_PROCESS\_ID](../../../extensibility/debugger/reference/ad-process-id.md)   
 [CONST\_GUID\_ARRAY](../../../extensibility/debugger/reference/const-guid-array.md)   
 [PROVIDER\_FLAGS](../../../extensibility/debugger/reference/provider-flags.md)   
 [PROVIDER\_PROCESS\_DATA](../../../extensibility/debugger/reference/provider-process-data.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)