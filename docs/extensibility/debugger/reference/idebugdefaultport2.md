---
title: "IDebugDefaultPort2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugDefaultPort2"
helpviewer_keywords: 
  - "IDebugDefaultPort2 인터페이스"
ms.assetid: 7b3452af-9a96-4c4c-9946-4339b72d3d7b
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDefaultPort2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 및 알림 기능을 포트를 서버에 액세스 하기 위한 여러 가지 방법을 제공 합니다.  
  
## 구문  
  
```  
IDebugDefaultPort2 : IDebugPort2  
```  
  
## 구현자 참고 사항  
 Visual Studio 프로그램에 액세스 하는 디버그 포트를 나타내는 데이 인터페이스를 구현 합니다.  사용자 지정 포트 공급자는 원격 디버깅을 처리 하는 경우이 인터페이스를 구현할 수도 있습니다.  
  
## 호출자에 대 한 참고 사항  
 메서드에 대 한 인수는 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md) 인터페이스는이 인터페이스를 제공 합니다.  호출 [QueryInterface](/visual-cpp/atl/queryinterface) 에 있는 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 인터페이스가이 인터페이스를 가져올 수도 있습니다.  
  
## 메서드에서 Vtable 순서  
 정의 된 메서드 외에 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md),이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetPortNotify](../../../extensibility/debugger/reference/idebugdefaultport2-getportnotify.md)|이 포트에서 포트 알림 인터페이스를 가져옵니다.|  
|[GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)|이 포트를 호스팅하는 서버에는 인터페이스를 가져옵니다.|  
|[QueryIsLocal](../../../extensibility/debugger/reference/idebugdefaultport2-queryislocal.md)|이 포트는 로컬 컴퓨터에서 실행 되 고 있는지 확인 합니다.|  
  
## 설명  
 이름이 "`IDebugDefaultPort2`" 약간의 misnomer, 기본 포트를 나타내는 것입니다.  "IDebugPort3" 라고  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)