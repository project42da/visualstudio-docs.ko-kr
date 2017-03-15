---
title: "방법: 중첩 된 프로젝트를 구현 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "구현 하는 중첩된 프로젝트"
  - "중첩 프로젝트 [Visual Studio SDK]"
ms.assetid: d20b8d6a-f0e0-4115-b3a3-edda893ae678
caps.latest.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 17
---
# 방법: 중첩 된 프로젝트를 구현 합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

사용자를 만들 때 중첩 된 프로젝트 형식에는 구현 해야 하는 몇 가지 추가 단계입니다.  부모 프로젝트 솔루션의 중첩 된 \(자식\) 프로젝트에 대 한이 같은 책임을 일부 사용 합니다.  부모 프로젝트의 솔루션에 유사한 프로젝트 컨테이너입니다.  특히, 솔루션 및 중첩 된 프로젝트의 계층 구조를 빌드할 부모 프로젝트 발생 해야 하는 여러 개의 이벤트입니다.  이러한 이벤트 다음 중첩 된 프로젝트를 만드는 프로세스를 설명 합니다.  
  
### 중첩 된 프로젝트를 만들려면  
  
1.  통합된 개발 환경 \(IDE\)를 호출 하 여 시작 하 고 파일 부모 프로젝트의 프로젝트 정보를 로드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory> 인터페이스입니다.  부모 프로젝트가 생성 되어 솔루션에 추가 합니다.  
  
    > [!NOTE]
    >  이 시점에서 너무 이른 하위 프로젝트를 만들기 전에 부모 프로젝트를 다시 만들어야 하므로 중첩된 프로젝트를 만들려면 부모 프로젝트에 대 한 프로세스입니다.  이 순서 다음 부모 프로젝트의 하위 프로젝트에 설정을 적용할 수 있습니다 하 고 필요한 경우 하위 프로젝트의 부모 프로젝트 정보 얻을 수 있습니다.  이 시퀀스에서 소스 코드 제어 \(SCC\) 및 솔루션 탐색기와 같은 클라이언트에서 필요한 경우입니다.  
  
     상위 프로젝트에 대 한 기다려야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject.OpenChildren%2A> 메서드를 프로젝트 또는 프로젝트는 중첩 된 \(자식\)을 만들 수 있습니다 IDE에서 호출할 수 있습니다.  
  
2.  IDE 호출 `QueryInterface` 의 부모 프로젝트에 대 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject>.  이 호출이 성공 하면, IDE 호출을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject.OpenChildren%2A> 메서드가 부모 모든 부모 프로젝트에 대 한 중첩 된 프로젝트를 엽니다.  
  
3.  부모 프로젝트 호출을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents.FireOnBeforeOpeningChildren%2A> 중첩 프로젝트 리스너에 알리는 방법입니다 만들려고 합니다.  예를 들어, 소스 코드 제어에서 솔루션 및 프로젝트 만들기 프로세스의 단계에서 발생 하는 경우 알아야 하는 이벤트를 수신 중입니다.  단계를 순서 대로 발생 하는 경우 솔루션 소스 코드 제어와 올바르게 등록 되지 않을 수 있습니다.  
  
4.  부모 프로젝트 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AddVirtualProject%2A> 메서드 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AddVirtualProjectEx%2A> 메서드는 하위 프로젝트의 각 합니다.  
  
     전달 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.__VSADDVPFLAGS> 에 있는 `AddVirtualProject` 가상 \(중첩된\) 프로젝트를 빌드에서 제외를 프로젝트 창 추가 해야 함을 표시 하려면 메서드 추가 소스 코드 제어 등을 합니다.  `VSADDVPFLAGS`중첩된 된 프로젝트의 가시성을 제어 하 고 연관 수 있는 기능을 나타내는 수 있습니다.  
  
     GUID는 부모 프로젝트 호출 부모 프로젝트의 프로젝트 파일에 저장 된 프로젝트에 있는 기존 하위 프로젝트를 다시 로드 하는 경우 `AddVirtualProjectEx`.  간의 유일한 차이점 `AddVirtualProject` 및 `AddVirtualProjectEX` 입니다 `AddVirtualProjectEX` 에서 부모 프로젝트를 지정 하는 매개 변수가 인스턴스 당 `guidProjectID` 사용할 수 있도록 자식 프로젝트에 대 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.GetProjectOfGuid%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.GetProjectOfProjref%2A> 제대로 작동 합니다.  
  
     사용할 수 있을 경우 없음 GUID, 중첩 된 새 프로젝트를 추가할 때 솔루션의 프로젝트에 대 한 만듭니다 같은 부모에 추가 됩니다.  해당 프로젝트의 프로젝트 파일에 있는 GUID를 유지 하는 부모 프로젝트의 책임입니다.  중첩 된 프로젝트를 삭제 하면 해당 프로젝트에 대 한 GUID도 삭제할 수 있습니다.  
  
5.  IDE 호출을 `M:Microsoft.VisualStudio.Shell.Interop.IVsParentProject.OpenChildren` 메서드를 각 하위 프로젝트의 부모 프로젝트.  
  
     부모 프로젝트를 구현 해야 합니다 `IVsParentProject` 프로젝트를 중첩 하려면.  하지만 호출 프로젝트 모 `QueryInterface` 에 대 한 `IVsParentProject` 상위 프로젝트 아래에 있는 있는 경우에.  호출을 처리 하는 솔루션 `IVsParentProject` 및 구현 되는 경우 호출 `OpenChildren` 중첩 된 프로젝트를 만들 수 있습니다.  `AddVirtualProjectEX`항상 호출 됩니다 `OpenChildren`.  절대로 부모 프로젝트 계층 구조를 만드는 이벤트를 순서 대로 유지 하 여 호출 해야 합니다.  
  
6.  IDE 호출을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A> 메서드는 자식 프로젝트입니다.  
  
7.  부모 프로젝트 호출을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents.FireOnAfterOpeningChildren%2A> 리스너에게 부모에 대해 하위 프로젝트를 만들 수 있는 방법입니다.  
  
8.  IDE 호출을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents.FireOnAfterOpenProject%2A> 방법에 모든 하위 프로젝트를 연 후에 부모 프로젝트.  
  
     아직 존재 하지 않을 경우, 부모 프로젝트를 호출 하 여 중첩 된 각 프로젝트에 대 한 GUID을 생성 합니다. `CoCreateGuid`.  
  
    > [!NOTE]
    >  `CoCreateGuid`COM API는 GUID를 만들어야 할 때 호출 됩니다.  자세한 내용은 `CoCreateGuid` 및 MSDN Library에서 Guid입니다.  
  
     부모 프로젝트이 GUID이 다음에 IDE를 열 때 검색 해야 하는 프로젝트 파일에 저장 됩니다.  호출 하 여 관련 된 자세한 내용은 4 단계를 참조 하십시오. `AddVirtualProjectEX` 를 검색 하는 `guidProjectID` 하위 프로젝트에 대해.  
  
9. <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> 메서드가 ItemID 부모에 대 한 다음 호출 규칙에 따라 사용에서 중첩된 프로젝트에 위임 하는 것입니다.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> 속성이 중첩의 상위 항목에서 호출 될 때 위임 하려는 프로젝트의 노드를 검색 합니다.  
  
     부모 및 자식 프로젝트를 프로그래밍 방식으로 인스턴스화되기 때문에 시점에서 중첩된 프로젝트에 대 한 속성을 설정할 수 있습니다.  
  
    > [!NOTE]
    >  중첩 된 프로젝트의 상황에 맞는 정보를 수신 하지 뿐 아니라 부모 프로젝트를 확인 하 여 해당 항목에 대 한 컨텍스트 있는 경우 요청할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>.  즉, 동적 도움말 추가 특성 및 특정 메뉴 옵션 중첩 된 개별 프로젝트에 추가할 수 있습니다.  
  
10. 계층 구조는 솔루션 탐색기에 표시를 내장 되어 있는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetNestedHierarchy%2A> 메서드.  
  
     계층을 통해 환경에 전달 하 여 `GetNestedHierarchy` 솔루션 탐색기에 표시 하기 위해 계층 구조를 빌드할 수 있습니다.  이러한 방법으로 솔루션 프로젝트 고 건물에 대 한 빌드 관리자가 관리할 수 있는 또는 소스 코드 제어에서 사용할 수 있는 프로젝트 파일 수 있음을 알고 있습니다.  
  
11. Project1 위해 모든 중첩된 프로젝트를 만든 제어 솔루션에 다시 전달 된 및 추가 대해이 프로세스가 반복 됩니다.  
  
     자식 하위 프로젝트에 대 한 중첩된 프로젝트 만들기에 대 한이 같은 프로세스를 발생 합니다.  하위 프로젝트 project1의 자식이, BuildProject1, 있는 경우이 경우에 BuildProject1 후 추가 하기 전에 만들어졌습니다.  프로세스 재귀적 이며 계층 구조 맨 위에서 아래로 빌드됩니다.  
  
     중첩 된 프로젝트는 닫을 때 사용자가 솔루션 또는 특정 프로젝트 자체에 다른 메서드를 때문에 `IVsParentProject`, <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject.CloseChildren%2A>, 호출 됩니다.  부모 프로젝트에 대 한 호출을 래핑하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.RemoveVirtualProject%2A> 메서드를 사용는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnBeforeClosingChildren%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterClosingChildren%2A> 중첩된 프로젝트가 닫혀 있는지 솔루션 이벤트 리스너에 알리는 방법입니다.  
  
 다음 항목에서는 중첩 된 프로젝트를 구현할 때 고려해 야 할 몇 가지 다른 개념을 다룹니다.  
  
 [중첩된 프로젝트 언로드 및 다시 로드에 대 한 고려 사항](../../extensibility/internals/considerations-for-unloading-and-reloading-nested-projects.md)  
  
 [중첩된 프로젝트에 대 한 마법사 지원](../../extensibility/internals/wizard-support-for-nested-projects.md)  
  
 [중첩된 프로젝트에 대 한 처리 명령 구현](../../extensibility/internals/implementing-command-handling-for-nested-projects.md)  
  
 [중첩된 프로젝트에 대 한 항목 추가 대화 상자를 필터링](../../extensibility/internals/filtering-the-additem-dialog-box-for-nested-projects.md)  
  
## 참고 항목  
 [에 항목 추가 된 새 항목 추가 대화 상자](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)   
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md)   
 [마법사 \(합니다. Vsz\) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)