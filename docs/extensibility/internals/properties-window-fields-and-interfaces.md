---
title: "속성 창의 필드 및 인터페이스 | Microsoft Docs"
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
  - "속성 창, 필드 및 인터페이스"
ms.assetid: 0328f0e5-2380-4a7a-a872-b547cb775050
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# 속성 창의 필드 및 인터페이스
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

모델 선택에 표시 되는 정보를 확인 하는  **속성** 윈도우 기반 IDE에서 포커스가 있는 창입니다.  모든 창과 개체 선택된 창에서 전역 선택 컨텍스트에 푸시된 선택 영역 컨텍스트 개체를 사용할 수 있습니다.  해당 창에 포커스가 있을 때 환경 선택 전역 컨텍스트 창 프레임의 값으로 업데이트 합니다.  포커스가 변경 될 때 따라서 선택 항목 컨텍스트를 하지 않습니다.  
  
## IDE에서 추적 선택  
 라는 서비스 창 프레임이 나 사이트를 IDE에서 소유 하 고 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection>.  열려 있는 다른 창으로 포커스를 변경 하거나 서로 다른 프로젝트 항목을 선택 하면 사용자가 발생 하면 선택한 변경 되는 방법을 표시 하는 다음 단계  **솔루션 탐색기**, 구현에 표시 되는 내용을 변경 하는  **속성** 창.  
  
1.  선택한 창을 호출에 사이 팅 되어 하면 VSPackage 만든 개체 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A> 를 <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection> 를 호출 <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection>.  
  
2.  선택한 창에서 제공 되는 선택 컨테이너 자체 만듭니다 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> 개체입니다.  선택 항목 있는 Vspackage를 호출 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> 환경에서 모든 수신기를 알리기 위해 포함 하는  **속성** 창에 변경.  또한 새 선택 영역에 관련 된 항목 및 계층 구조 정보에 액세스할 수 있습니다.  
  
3.  호출 <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> 하 고 선택한 계층 항목을 전달 하는 `VSHPROPID_BrowseObject` 매개 변수를 채우고는 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> 개체.  
  
4.  개체에서 파생의 [IDispatch Interface](http://msdn.microsoft.com/ko-kr/ebbff4bc-36b2-4861-9efa-ffa45e013eb5) 에 대 한 반환 됩니다 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> 항목에서 요청한 래핑하는 환경에 대 한는 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> \(다음 단계 참조\).  호출이 실패 하면 환경 두 번째 호출 `IVsHierarchy::GetProperty`, 선택 컨테이너 전달 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> 계층 구조 항목을 제공 합니다.  
  
     VSPackage 만들지 않는 프로젝트 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> VSPackage 환경 제공 된 창에이 구현 하기 때문에 \(예를 들어,  **솔루션 탐색기**\) 생성 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> 을 대신 합니다.  
  
5.  메서드를 호출 하는 환경 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> 개체를 가져올 수 있는 `IDispatch` 인터페이스를 채우는 데는  **속성** 창.  
  
 값의 경우는  **속성** 창이 변경 되 고 VSPackages 구현 `IVsTrackSelectionEx::OnElementValueChangeEx` 및 `IVsTrackSelectionEx::OnSelectionChangeEx` 변경 요소 값을 보고 합니다.  다음 환경 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> 또는 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> 에 표시 되는 정보를 유지 하는  **속성** 창에서는 속성 값을 동기화 합니다.  자세한 내용은 [속성 창에서 속성 값을 업데이트합니다.](../../misc/updating-property-values-in-the-properties-window.md)를 참조하십시오.  
  
 다른 선택 하에서 프로젝트 항목  **솔루션 탐색기** 해당 항목에 관련 된 속성을 표시 하려면 드롭다운 목록에서 사용할 수를 사용 하 여 양식 또는 문서 창에서 다른 개체를 선택할 수도 있습니다의  **속성이** 창입니다.  자세한 내용은 [속성 창의 개체 목록](../../extensibility/internals/properties-window-object-list.md)를 참조하십시오.  
  
 정보가 표시 되는 방식을 변경할 수 있습니다의  **속성** 알파벳에서 창의 눈금에 범주 형, 및 사용할 수 있는 경우 선택한 개체에 대 한 속성 페이지에서 적절 한 단추를 클릭 하 여 열 수도 있습니다의  **속성** 창.  자세한 내용은 [속성 창 단추](../../extensibility/internals/properties-window-buttons.md) 및 [속성 페이지](../../extensibility/internals/property-pages.md)을 참조하십시오.  
  
 맨 마지막으로  **속성** 창에서 선택한 필드에 대 한 설명도 들어 있습니다는  **속성** 표 창.  자세한 내용은 [속성 창에서 필드 설명 가져오기](../../misc/getting-field-descriptions-from-the-properties-window.md)를 참조하십시오.  
  
## 참고 항목  
 [속성 확장](../../extensibility/internals/extending-properties.md)