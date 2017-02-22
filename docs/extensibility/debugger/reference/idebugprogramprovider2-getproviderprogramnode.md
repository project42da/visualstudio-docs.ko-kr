---
title: "IDebugProgramProvider2::GetProviderProgramNode | Microsoft Docs"
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
  - "IDebugProgramProvider2::GetProviderProgramNode"
helpviewer_keywords: 
  - "IDebugProgramProvider2::GetProviderProgramNode"
ms.assetid: e62e8e83-acbb-4c52-aedf-ffbd4670db29
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgramProvider2::GetProviderProgramNode
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

특정 프로그램에 대 한 프로그램 노드를 검색합니다.  
  
## 구문  
  
```cpp  
HRESULT GetProviderProgramNode(  
   PROVIDER_FLAGS       Flags,  
   IDebugDefaultPort2*  pPort,  
   AD_PROCESS_ID        processId,  
   REFGUID              guidEngine,  
   UINT64               programId,  
   IDebugProgramNode2** ppProgramNode  
);  
```  
  
```c#  
int GetProviderProgramNode(  
   enum_PROVIDER_FLAGS    Flags,  
   IDebugDefaultPort2     pPort,  
   AD_PROCESS_ID          ProcessId,  
   ref Guid               guidEngine,  
   ulong                  programId,  
   out IDebugProgramNode2 ppProgramNode  
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
  
 `pPort`  
 \[in\] 호출 프로세스가 포트에서 실행 됩니다.  
  
 `processId`  
 \[in\] [AD\_PROCESS\_ID](../../../extensibility/debugger/reference/ad-process-id.md) 구조를 프로그램에 포함 되어 있는 프로세스의 ID를 보유 합니다.  
  
 `guidEngine`  
 \[in\] \(있는 경우\)에서 프로그램 연결 된 디버그 엔진의 GUID입니다.  
  
 `programId`  
 \[in\] 프로그램을 프로그램이 노드를 가져올 ID입니다.  
  
 `ppProgramNode`  
 \[out\] [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 프로그램을 요청 된 노드가 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)   
 [PROVIDER\_FLAGS](../../../extensibility/debugger/reference/provider-flags.md)   
 [AD\_PROCESS\_ID](../../../extensibility/debugger/reference/ad-process-id.md)   
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)