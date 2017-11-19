---
title: "방법: 중첩 된 프로젝트를 구현 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- nested projects, implementing
- projects [Visual Studio SDK], nesting
ms.assetid: d20b8d6a-f0e0-4115-b3a3-edda893ae678
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 26456122d8b2cb0e89cfcda929cf68306959a31e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-implement-nested-projects"></a>방법: 중첩 된 프로젝트를 구현 합니다.
만들 때 구현 해야 하는 몇 가지 추가 단계는 중첩 된 프로젝트 형식에는 합니다. 부모 프로젝트는 솔루션의 중첩 된 (자식) 프로젝트에 있는 동일한 책임이 있는 몇 가지에 적용 됩니다. 부모 프로젝트는 솔루션에 유사한 프로젝트의 컨테이너입니다. 특히, 중첩 된 프로젝트의 계층 구조를 빌드하는 부모 프로젝트 및 솔루션에서 발생 해야 하는 여러 가지 이벤트 있습니다. 이러한 이벤트는 중첩 된 프로젝트를 만들기 위한 다음 프로세스에 설명 되어 있습니다.  
  
### <a name="to-create-nested-projects"></a>중첩 된 프로젝트를 만들려면  
  
1.  호출 하 여 부모 프로젝트의 프로젝트 파일 및 시작 정보를 로드 하는 통합된 개발 환경 (IDE)는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory> 인터페이스입니다. 부모 프로젝트 생성 되어 솔루션에 추가 합니다.  
  
    > [!NOTE]
    >  이 시점에서 하위 프로젝트를 만들기 전에 부모 프로젝트를 만들어야 하기 때문에 중첩 된 프로젝트를 만들려면 부모 프로젝트에 대 한 프로세스에는 너무 이릅니다. 이 시퀀스는 부모 프로젝트 하위 프로젝트에 설정을 적용할 수 및 필요한 경우 하위 프로젝트 부모 프로젝트에서 정보를 얻을 수 있습니다. 이 순서는 경우 필요에에 따라 소스 코드 제어 (SCC), 솔루션 탐색기 등의 클라이언트입니다.  
  
     부모 프로젝트에 대해 기다려야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject.OpenChildren%2A> 프로젝트 또는 프로젝트의 중첩 된 (자식)을 만들 수 있습니다는 IDE에 의해 호출 될 메서드입니다.  
  
2.  IDE 호출 `QueryInterface` 에 대 한 부모 프로젝트에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject>합니다. 경우이 호출이 성공 하면 IDE 호출은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject.OpenChildren%2A> 부모 프로젝트에 대 한 중첩 된 프로젝트의 모든 열을 부모 메서드.  
  
3.  프로젝트에서 호출 하는 부모는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents.FireOnBeforeOpeningChildren%2A> 프로젝트를 중첩 하는 수신기에 알리기 위해 메서드를 만들 수는 있습니다. 예를 들어 SCC, 솔루션 및 프로젝트 만들기 프로세스의 단계 순서에서 발생 하는 경우에 대해 알아야 이러한 이벤트로 수신 합니다. 단계를 순서 대로 발생 한 경우 솔루션 등록 되지 소스 코드 제어로 올바르게 합니다.  
  
4.  부모 프로젝트 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AddVirtualProject%2A> 메서드 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AddVirtualProjectEx%2A> 해당 하위 프로젝트의 각 메서드.  
  
     전달 <xref:Microsoft.VisualStudio.Shell.Interop.__VSADDVPFLAGS> 에 `AddVirtualProject` 가상 (중첩 된) 프로젝트의 빌드에서 제외 프로젝트 창에 추가 되어야 함을 나타내도록 메서드를 소스 코드 제어에 추가 합니다. `VSADDVPFLAGS`중첩 된 프로젝트의 표시 유형을 제어 하 고 관련 된 기능에 설명 되었을 수 있습니다.  
  
     프로젝트 GUID 부모 프로젝트의 프로젝트 파일을 호출 하 여 부모 프로젝트에 저장 된 지정 된 이전에 기존 자식 프로젝트 다시 로드 하는 경우 `AddVirtualProjectEx`합니다. 간의 유일한 차이점 `AddVirtualProject` 및 `AddVirtualProjectEX` 은 `AddVirtualProjectEX` 지정 하는 부모 프로젝트를 사용 하도록 설정 하려면 매개 변수는 인스턴스당 `guidProjectID` 사용할 수 있도록 자식 프로젝트에 대 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.GetProjectOfGuid%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.GetProjectOfProjref%2A> 함수 올바르게 합니다.  
  
     GUID가 사용 가능한 경우, 솔루션 시간에는 프로젝트에 대 한 솔루션이 생성 새 중첩 된 프로젝트를 추가할 때와 같은 부모에 추가 됩니다. 해당 프로젝트의 프로젝트 파일에 GUID를 유지 하는 부모 프로젝트의 작업은 중첩 된 프로젝트를 삭제 하면 해당 프로젝트에 대 한 GUID도 삭제할 수 있습니다.  
  
5.  IDE 호출은 `M:Microsoft.VisualStudio.Shell.Interop.IVsParentProject.OpenChildren` 부모 프로젝트의 각 자식 프로젝트 메서드.  
  
     부모 프로젝트를 구현 해야 `IVsParentProject` 프로젝트 중첩 하려는 경우. 하지만 호출 되지 프로젝트 부모 `QueryInterface` 에 대 한 `IVsParentProject` 부모 프로젝트 아래에 있는 경우에 합니다. 에 대 한 호출을 처리 하는 솔루션 `IVsParentProject` 구현 되는 경우 호출 하 고 `OpenChildren` 중첩 된 프로젝트를 만들 수 있습니다. `AddVirtualProjectEX`항상 라고 `OpenChildren`합니다. 부모 프로젝트 계층 구조 생성 이벤트를 순서로 유지 하기는 호출 되지 되어야 합니다.  
  
6.  IDE 호출은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A> 자식 프로젝트에서 메서드.  
  
7.  프로젝트에서 호출 하는 부모는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents.FireOnAfterOpeningChildren%2A> 메서드를 부모에 대 한 하위 프로젝트를 만들었다고 수신기에 알립니다.  
  
8.  IDE 호출은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents.FireOnAfterOpenProject%2A> 모든 자식 프로젝트가 열린 후 부모 프로젝트에서 메서드.  
  
     부모 프로젝트를 호출 하 여 중첩 된 각 프로젝트에 대 한 GUID를 만들고 이미 존재 하지 않는 경우 `CoCreateGuid`합니다.  
  
    > [!NOTE]
    >  `CoCreateGuid`GUID는 만들 때에 COM API 호출 됩니다. 자세한 내용은 참조 `CoCreateGuid` 및 MSDN 라이브러리의 Guid입니다.  
  
     부모 프로젝트 다음에 IDE에서 열려 있는 검색할 해당 프로젝트 파일에이 GUID를 저장 합니다. 호출에 관련 된 자세한 내용은 4 단계를 참조 `AddVirtualProjectEX` 검색 하는 `guidProjectID` 자식 프로젝트에 대 한 합니다.  
  
9. <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> 다음 메서드는 부모 ItemID에 대 한 규칙에 따라 위임 하에 중첩 된 프로젝트에 있습니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> 부모에서 호출 될 때에 위임 하려는 하는 프로젝트를 중첩 하는 노드의 속성을 검색 합니다.  
  
     부모 및 자식 프로젝트 프로그래밍 방식으로 인스턴스화됩니다 때문에 시점에서 중첩 된 프로젝트에 대 한 속성을 설정할 수 있습니다.  
  
    > [!NOTE]
    >  컨텍스트 정보는 중첩 된 프로젝트에서 수신지 않습니다 뿐 아니라 부모 프로젝트 있는지 확인 하 여 해당 항목에 대 한 컨텍스트를 요청할 수도 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>합니다. 이런 방식으로 개별 중첩 된 프로젝트에 추가 동적 도움말 특성 및 관련 된 메뉴 옵션을 추가할 수 있습니다.  
  
10. 계층을 호출 하 여 솔루션 탐색기에 표시 하기 위해 만들어집니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetNestedHierarchy%2A> 메서드.  
  
     통해 환경에 계층 구조를 전달 하면 `GetNestedHierarchy` 솔루션 탐색기에 표시 하기 위해 계층을 형성 하 합니다. 이러한 방식으로 솔루션 알고 프로젝트 또는 존재 하는 및 만들기에 대 한 빌드 관리자가 관리할 수를 소스 코드 제어에서 설정 해야 프로젝트의 파일을 허용할 수 있습니다.  
  
11. 프로젝트 1에 대 한 모든 중첩 된 프로젝트를 만든 제어 솔루션 다시 전달 하 고 Project2에 대해이 프로세스가 반복 됩니다.  
  
     중첩 된 프로젝트를 만들기 위한 동일한이 프로세스는 자식 있는 자식 프로젝트에 대 한 발생 합니다. 이 경우 Project1의 하위 형식인 BuildProject1 자식 프로젝트가 있으면은 생성 되기 BuildProject1 뒤와 Project2 앞입니다. 프로세스는 재귀 및 계층 구조 아래로 위쪽에서 작성 됩니다.  
  
     사용자 솔루션 닫혀 있지 않거나 특정 프로젝트 자체는 또 다른 방법은에 때문에 중첩 된 프로젝트를 닫을 때 `IVsParentProject`, <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject.CloseChildren%2A>, 호출 됩니다. 부모 프로젝트에 대 한 호출을 래핑하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.RemoveVirtualProject%2A> 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnBeforeClosingChildren%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterClosingChildren%2A> 중첩된 프로젝트 종결 되 고 솔루션 이벤트를 수신기에 알리기 위해 메서드.  
  
 다음 항목은 중첩 된 프로젝트를 구현할 때 고려해 야 할 다른 몇 가지 개념을 다루는:  
  
 [중첩된 프로젝트 언로드 및 다시 로드에 대한 고려 사항](../../extensibility/internals/considerations-for-unloading-and-reloading-nested-projects.md)  
  
 [중첩된 프로젝트에 대한 마법사 지원](../../extensibility/internals/wizard-support-for-nested-projects.md)  
  
 [중첩된 프로젝트에 대한 명령 처리 구현](../../extensibility/internals/implementing-command-handling-for-nested-projects.md)  
  
 [중첩된 프로젝트에 대한 AddItem 필터링 대화 상자](../../extensibility/internals/filtering-the-additem-dialog-box-for-nested-projects.md)  
  
## <a name="see-also"></a>참고 항목  
 [항목에 추가 된 새 항목 추가 대화 상자](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)   
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md)   
 [마법사(.Vsz) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)