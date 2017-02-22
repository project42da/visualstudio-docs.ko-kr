---
title: "시작 된 후 연결 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로그램에 연결 되는 디버그 엔진"
ms.assetid: 5a3600a1-dc20-4e55-b2a4-809736a6ae65
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# 시작 된 후 연결
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버그 세션 프로그램이 실행 된 후에 디버그 엔진 \(DE\) 언급된 프로그램에 연결할 준비가 되었습니다.  
  
## 디자인 결정  
 공유 주소 공간 내에서 통신 편리 하므로 디버그 세션 및 DE, 또는 DE와 프로그램 사이의 통신을 용이 하 게 하는 더 많은 것이 수 있습니다 여부를 결정 해야 합니다.  다음 중 선택 하십시오.  
  
-   디버그 세션 하는 DE 간의 통신을 용이 하 게 하는 것 경우 디버그 세션은 DE co\-creates 하 고 프로그램에 연결 하는 DE 묻는 메시지가 나타납니다.  이 디버그 세션 및 DE 함께 하나 이상의 주소 공간이 런타임 환경 및 프로그램의 다른 함께 둡니다.  
  
-   다음 것은 DE와 프로그램 간의 통신을 용이 하 게 하는 경우 런타임 환경에서 DE co\-creates.  주소 공간에는 SDM DE, 런타임 환경 및 프로그램 다른 함께 둡니다.  일반적으로 스크립트 언어를 실행 하는 인터프리터를 함께 구현 되는 DE입니다.  
  
    > [!NOTE]
    >  어떻게 프로그램에는 DE이 연결 구현에 따라 다릅니다.  DE와 프로그램 간의 통신에도 구현에 따라 다릅니다.  
  
## 구현  
 프로그래밍 방식으로 하면 세션 디버그 매니저 \(SDM\)을 먼저 받습니다는 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) 시작 되는 프로그램을 나타내는 개체를 호출을 [연결](../../extensibility/debugger/reference/idebugprogram2-attach.md) 메서드를 전달 하 여는 [IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md) 나중에 객체를 사용 하는 디버그 이벤트는 SDM을 다시 전달 하.  그런 다음 `IDebugProgram2::Attach` 메서드가 [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) 메서드를 호출합니다.  SDM을 받는 방법을 대 한 자세한 내용은 `IDebugProgram2` 인터페이스를 참조 하십시오 [포트에 게 알리는](../../extensibility/debugger/notifying-the-port.md).  
  
 사용자 DE DE는 스크립트 인터프리터 일부 이기 때문에 일반적으로 디버깅 중인 프로그램의 동일한 주소 공간에서 실행 하는 경우는 `IDebugProgramNodeAttach2::OnAttach` 메서드가 반환 `S_FALSE`, 연결 프로세스가 완료 된 것을 나타내는.  
  
 반면, DE는 SDM의 주소 공간에서 실행 하는 경우는 `IDebugProgramNodeAttach2::OnAttach` 메서드가 반환 `S_OK` 나는 [IDebugProgramNodeAttach2](../../extensibility/debugger/reference/idebugprogramnodeattach2.md) 인터페이스에 전혀 구현 되지 않았습니다의 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) 디버깅 중인 프로그램에 연결 된 개체입니다.  이 경우에 [연결](../../extensibility/debugger/reference/idebugengine2-attach.md) 첨부 작업을 완료 하려면 메서드가 호출 되어 결국.  
  
 후자의 경우 호출 해야는 [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md) 메서드를는 `IDebugProgram2` 에 전달 된 개체는 `IDebugEngine2::Attach` 메서드, 저장소는 `GUID` 로컬 프로그램을 한이 반환 `GUID` 때의 `IDebugProgram2::GetProgramId` 메서드가이 개체에서 호출 이후에.  `GUID` 다양 한 디버그 구성 요소에서 프로그램을 고유 하 게 식별 하는 데 사용 됩니다.  
  
 참고는 `IDebugProgramNodeAttach2::OnAttach` 반환 메서드 `S_FALSE`의 `GUID` 의 프로그램을 사용 하는 메서드로 전달 되 고는 `IDebugProgramNodeAttach2::OnAttach` 설정 하는 메서드는 `GUID` 로컬 프로그램 개체에.  
  
 DE는 지금 프로그램 및 모든 시작 이벤트를 보낼 준비가 연결 되어 있습니다.  
  
## 참고 항목  
 [프로그램에 직접 연결](../../extensibility/debugger/attaching-directly-to-a-program.md)   
 [포트에 게 알리는](../../extensibility/debugger/notifying-the-port.md)   
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)   
 [IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)   
 [연결](../../extensibility/debugger/reference/idebugprogram2-attach.md)   
 [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [IDebugProgramNodeAttach2](../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)   
 [연결](../../extensibility/debugger/reference/idebugengine2-attach.md)