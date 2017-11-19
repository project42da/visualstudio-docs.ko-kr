---
title: IDebugProgramProvider2::GetProviderProgramNode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramProvider2::GetProviderProgramNode
helpviewer_keywords: IDebugProgramProvider2::GetProviderProgramNode
ms.assetid: e62e8e83-acbb-4c52-aedf-ffbd4670db29
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4ad5540d1f93e44b069cac4873880e9db9d96919
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogramprovider2getproviderprogramnode"></a>IDebugProgramProvider2::GetProviderProgramNode
특정 프로그램에 대 한 프로그램 노드를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetProviderProgramNode(  
   PROVIDER_FLAGS       Flags,  
   IDebugDefaultPort2*  pPort,  
   AD_PROCESS_ID        processId,  
   REFGUID              guidEngine,  
   UINT64               programId,  
   IDebugProgramNode2** ppProgramNode  
);  
```  
  
```csharp  
int GetProviderProgramNode(  
   enum_PROVIDER_FLAGS    Flags,  
   IDebugDefaultPort2     pPort,  
   AD_PROCESS_ID          ProcessId,  
   ref Guid               guidEngine,  
   ulong                  programId,  
   out IDebugProgramNode2 ppProgramNode  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Flags`  
 [in] 플래그의 조합 된 [PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md) 열거 합니다. 다음 플래그는이 호출에 대 한 일반적인:  
  
|플래그|설명|  
|----------|-----------------|  
|`PFLAG_REMOTE_PORT`|호출자에 게 원격 컴퓨터에서 실행 됩니다.|  
|`PFLAG_DEBUGGEE`|호출자에 게 현재 디버깅 중인 (각 노드에 대해 마샬링하는 작업에 대 한 추가 정보가 반환 됩니다).|  
|`PFLAG_ATTACHED_TO_DEBUGGEE`|호출자에 연결 했지만 디버거에서 실행 되지 않습니다.|  
  
 `pPort`  
 [in] 포트는 호출 프로세스에서 실행 됩니다.  
  
 `processId`  
 [in] [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) 구조에 프로그램을 포함 하는 프로세스의 ID를 보유 합니다.  
  
 `guidEngine`  
 [in] 프로그램 (있는 경우)에 연결 된 디버그 엔진의 GUID입니다.  
  
 `programId`  
 [in] 프로그램을 가져올 프로그램 노드 ID입니다.  
  
 `ppProgramNode`  
 [out] [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 요청 된 프로그램이 노드를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)   
 [PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md)   
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)   
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)