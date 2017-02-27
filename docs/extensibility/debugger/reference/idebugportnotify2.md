---
title: "IDebugPortNotify2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortNotify2"
helpviewer_keywords: 
  - "IDebugPortNotify2 인터페이스"
ms.assetid: 43278b79-bf16-4c08-bcf1-6f7f7a17feab
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugPortNotify2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스를 등록 하거나 실행 중인 포트를 디버깅할 수 있는 프로그램의 등록을 취소 합니다.  
  
## 구문  
  
```  
IDebugPortNotify2 : IUnknown  
```  
  
## 구현자 참고 사항  
 사용자 지정 포트 공급자 추가 및 포트에서 프로그램 제거를 지원 하기 위해이 인터페이스를 구현 합니다.  일반적으로 구현 하는 동일한 개체에서 구현 되는 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 호출을 [QueryInterface](/visual-cpp/atl/queryinterface) 에 `IDebugPort2` 인터페이스는이 인터페이스를 반환 합니다.  또한, 호출 [GetPortNotify](../../../extensibility/debugger/reference/idebugdefaultport2-getportnotify.md) 이 인터페이스를 반환 합니다.  디버그 엔진의 매개 변수로이 인터페이스를 볼 수 있습니다 [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md).  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugPortNotify2`.  
  
|메서드|설명|  
|---------|--------|  
|[AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)|디버깅할 수 있는 프로그램이 실행 되는 포트를 등록 합니다.|  
|[RemoveProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)|실행 중인 포트에서 디버깅할 수 있는 프로그램의 등록을 취소 합니다.|  
  
## 설명  
 디버그 포트 프로그램이 로드 되거나 언로드될 때를 알 수 없는 한, 사용자 지정 포트 공급자는이 인터페이스를 구현 해야 합니다.  이 인터페이스를 사용 하 여 특정 포트를 통한 디버깅을 위해 로드 되는 모든 프로그램을 추적 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)