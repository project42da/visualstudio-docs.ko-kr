---
title: "IDebugProgramNodeAttach2 | Microsoft Docs"
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
  - "IDebugProgramNodeAttach2"
helpviewer_keywords: 
  - "IDebugProgramNodeAttach2 인터페이스"
ms.assetid: 46b37ac9-a026-4ad3-997b-f19e2f8deb73
caps.latest.revision: 3
caps.handback.revision: 3
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgramNodeAttach2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로그램 노드가 연결 된 프로그램에 연결 하려고 수 있습니다.  
  
## 구문  
  
```  
IDebugProgramNodeAttach2 : IUnknown  
```  
  
## 구현자 참고 사항  
 이 인터페이스를 구현 하는 클래스에서 구현에서 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 인터페이스 연결 작업 알림을 수신 하 고 연결 작업을 취소할 수 있는 기회를 제공 합니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 얻을 `QueryInterface` 메서드에서 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 개체입니다.  [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) 하기 전에 메서드를 호출 해야 합니다는 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 프로그램 노드 연결 프로세스를 중지할 수 있습니다. 메서드.  
  
## 메서드에서 Vtable 순서  
 이 인터페이스에 다음 메서드를 구현합니다.  
  
|메서드|설명|  
|---------|--------|  
|[OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)|관련된 프로그램에 연결 또는 연결 프로세스를 지연의 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 방법입니다.|  
  
## 설명  
 기본 설정된 대신 하 여 사용 되지 않는이 인터페이스는 [Attach\_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md) 메서드가 있습니다.  모든 디버그 엔진을 항상 로드 되는 `CoCreateInstance` 기능, 즉,는 디버깅 중인 프로그램의 주소 공간 범위 밖에 인스턴스화되는.  
  
 에 이미 구현 되어 있는 경우는 `IDebugProgramNode2::Attach_V7` 방법을 설정 했습니다만 `GUID` , 다음만 디버깅 중인 프로그램의의 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) 메서드를 구현할 수는.  
  
 에 이미 구현 되어 있는 경우는 `IDebugProgramNode2::Attach_V7` 메서드는 제공 된 콜백 인터페이스를 사용 하 고 해당 기능을 구현 하는 이동 해야는 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드 및 `IDebugProgramNodeAttach2` 구현할 인터페이스가 없습니다.  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [Attach\_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md)