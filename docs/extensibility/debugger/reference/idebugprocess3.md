---
title: "IDebugProcess3 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProcess3"
helpviewer_keywords: 
  - "IDebugProcess3 인터페이스"
ms.assetid: 7bd6b952-cf34-4e66-b8f6-d472dac3748f
caps.latest.revision: 24
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 24
---
# IDebugProcess3
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 실행 중인 프로세스와 프로그램을 나타냅니다.  이 인터페이스에서 여러 가지 방법으로 대체 존재는 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 인터페이스입니다.  이 과정에서 프로그램을 모두 제어할을 수 있습니다.  
  
> [!NOTE]
>  [계속](../../../extensibility/debugger/reference/idebugprogram2-continue.md) [실행](../../../extensibility/debugger/reference/idebugprogram2-execute.md), 및 [단계](../../../extensibility/debugger/reference/idebugprogram2-step.md) 메서드는 사용 되지 않으며 더 이상 사용 해야 합니다.  해당 메서드를 사용 하 여에 `IDebugProcess3` 대신 인터페이스입니다.  
  
## 구문  
  
```  
IDebugProcess3 : IDebugProcess2  
```  
  
## 구현자 참고 사항  
 프로그램을 그룹으로 관리 하는 사용자 지정 포트 공급자가이 인터페이스를 구현 합니다.  프로그램을 그룹으로 관리 하는 경우 식 계산기에 대 한 언어 설정 및 실행을 제어할 수 있습니다.  포트 공급자가이 인터페이스를 구현 해야 합니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스 세션 디버그 관리자 \(SDM\)가 주로이 과정에서 식별 된 프로그램 그룹 상호 작용 하기 위해 호출 됩니다.  
  
 호출 [QueryInterface](/visual-cpp/atl/queryinterface) 에 있는 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) 이 인터페이스를 가져올 수 있는 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 상속 된 메서드 외에 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md), `IDebugProcess3` 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[계속](../../../extensibility/debugger/reference/idebugprocess3-continue.md)|실행 하거나 프로세스를 통해 단계별로 실행을 계속 합니다.|  
|[실행](../../../extensibility/debugger/reference/idebugprocess3-execute.md)|프로세스의 실행을 시작합니다.|  
|[단계](../../../extensibility/debugger/reference/idebugprocess3-step.md)|명령 또는 문 과정에서 한 단계를 전달합니다.|  
|[GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md)|디버깅 하기 위해 프로세스를 시작한 된 이유를 가져옵니다.|  
|[SetHostingProcessLanguage](../../../extensibility/debugger/reference/idebugprocess3-sethostingprocesslanguage.md)|디버그 엔진 로드를 적절 한 식 계산기 호스팅 언어를 설정 합니다.|  
|[GetHostingProcessLanguage](../../../extensibility/debugger/reference/idebugprocess3-gethostingprocesslanguage.md)|이 프로세스에 대해 현재 설정 된 언어 집합을 검색 합니다.|  
|[DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md)|편집 하며 계속 \(ENC\)이이 프로세스에 대해 사용할 수 없습니다.<br /><br /> 사용자 지정 포트 공급자가이 메서드를 구현 하지 않습니다 \(항상 반환 해야 `E_NOTIMPL`\).|  
|[GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md)|이 프로세스에 대해 ENC 상태를 가져옵니다.<br /><br /> 사용자 지정 포트 공급자가이 메서드를 구현 하지 않습니다 \(항상 반환 해야 `E_NOTIMPL`\).|  
|[GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md)|사용할 수 있는 디버깅 엔진에 대 한 고유 식별자의 배열을 검색합니다.|  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)