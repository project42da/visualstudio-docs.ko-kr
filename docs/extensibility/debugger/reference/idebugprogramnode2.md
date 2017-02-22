---
title: "IDebugProgramNode2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgramNode2"
helpviewer_keywords: 
  - "IDebugProgramNode2 인터페이스"
ms.assetid: 80e511d8-9b40-4a85-aa5d-952fa5ee6ae7
caps.latest.revision: 20
caps.handback.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgramNode2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 디버깅할 수 있는 프로그램을 나타냅니다.  
  
## 구문  
  
```  
IDebugProgramNode2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 또는 사용자 지정 포트 공급자 디버깅 하는 프로그램을 나타내는 데이 인터페이스를 구현 합니다.  이 인터페이스를 구현 하는 동일한 개체에서 일반적으로 구현 되는 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 인터페이스입니다.  이 인터페이스를 등록 된 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 를 호출 하 여 [PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md).  
  
## 호출자에 대 한 참고 사항  
 호출 [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md) 이 인터페이스를 반환 합니다.  이 인터페이스에 대 한 호출을 통해 사용자 지정 포트 공급자 받는 [AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md).  이 인터페이스를 통해 호출 하는 DE 수신 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md).  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugProgramNode2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetProgramName](../../../extensibility/debugger/reference/idebugprogramnode2-getprogramname.md)|프로그램의 이름을 가져옵니다.|  
|[GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)|프로그램을 호스팅하는 프로세스의 이름을 가져옵니다.|  
|[GetHostPid](../../../extensibility/debugger/reference/idebugprogramnode2-gethostpid.md)|프로그램을 호스팅하는 프로세스의 시스템 프로세스 id를 가져옵니다.|  
|[GetHostMachineName\_V7](../../../extensibility/debugger/reference/idebugprogramnode2-gethostmachinename-v7.md)|사용 되지 않습니다.  사용 하지 않습니다.|  
|[Attach\_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md)|사용 되지 않습니다.  사용 하지 않습니다.  참조는 [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md) 는 다른 방법에 대 한 인터페이스입니다.|  
|[GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)|이름 및이 프로그램을 실행 하는 DE의 식별자를 가져옵니다.|  
|[DetachDebugger\_V7](../../../extensibility/debugger/reference/idebugprogramnode2-detachdebugger-v7.md)|사용 되지 않습니다.  사용 하지 않습니다.|  
  
## 설명  
 일반적으로 세션 디버그 매니저 \(SDM\)를 호출 합니다. [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md) 이 인터페이스를 가져올 수 있습니다.  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)   
 [RemoveProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)   
 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)   
 [PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md)