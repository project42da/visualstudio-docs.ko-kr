---
title: "프로젝트 항목의 속성이 유지 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties, adding to a project item
- project items, adding properties
ms.assetid: d7a0f2b0-d427-4d49-9536-54edfb37c0f3
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 61a477fa760a2ef9026b06facc8bc592706c5dd3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="persisting-the-property-of-a-project-item"></a>프로젝트 항목의 속성이 유지
소스 파일의 작성자와 같은 프로젝트 항목에 추가 하는 속성을 유지 하려는 경우. 이렇게 하려면 프로젝트 파일에 속성을 저장 합니다.  
  
 프로젝트 파일에서 속성을 유지 하려면 첫 번째 단계는 프로젝트의 계층 구조를 가져올 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 인터페이스입니다. 자동화를 사용 하거나 사용 하 여이 인터페이스를 가져올 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>합니다. 인터페이스를 가져오고 나면 현재 선택한 프로젝트 항목을 확인 하려면 사용할 수 있습니다. 프로젝트 항목 ID가 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetItemAttribute%2A> 는 속성을 추가 합니다.  
  
 VsPkg.cs 속성을 저장 하면 다음 절차에서 `Author` 값과 `Tom` 프로젝트 파일에 있습니다.  
  
### <a name="to-obtain-the-project-hierarchy-with-the-dte-object"></a>DTE 개체를 프로젝트 계층 구조를 가져오려면  
  
1.  VSPackage에 다음 코드를 추가 합니다.  
  
    ```csharp  
    EnvDTE.DTE dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));  
    EnvDTE.Project project = dte.Solution.Projects.Item(1);  
  
    string uniqueName = project.UniqueName;  
    IVsSolution solution = (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));  
    IVsHierarchy hierarchy;  
    solution.GetProjectOfUniqueName(uniqueName, out hierarchy);  
    ```  
  
### <a name="to-persist-the-project-item-property-with-the-dte-object"></a>DTE 개체와 프로젝트 항목 속성을 유지 하려면  
  
1.  이전 절차에서 메서드에 지정 된 코드에 다음 코드를 추가 합니다.  
  
    ```csharp  
    IVsBuildPropertyStorage buildPropertyStorage =   
        hierarchy as IVsBuildPropertyStorage;  
    if (buildPropertyStorage != null)  
    {  
        uint itemId;  
        string fullPath = (string)project.ProjectItems.Item(  
            "VsPkg.cs").Properties.Item("FullPath").Value;  
        hierarchy.ParseCanonicalName(fullPath, out itemId);  
        buildPropertyStorage.SetItemAttribute(itemId, "Author", "Tom");  
    }  
    ```  
  
### <a name="to-obtain-the-project-hierarchy-using-ivsmonitorselection"></a>IVsMonitorSelection를 사용 하 여 프로젝트 계층 구조를 가져오려면  
  
1.  VSPackage에 다음 코드를 추가 합니다.  
  
    ```csharp  
    IVsHierarchy hierarchy = null;  
    IntPtr hierarchyPtr = IntPtr.Zero;  
    IntPtr selectionContainer = IntPtr.Zero;  
    uint itemid;  
  
    // Retrieve shell interface in order to get current selection  
    IVsMonitorSelection monitorSelection =     Package.GetGlobalService(typeof(SVsShellMonitorSelection)) as     IVsMonitorSelection;  
    if (monitorSelection == null)  
        throw new InvalidOperationException();  
  
    try  
    {  
        // Get the current project hierarchy, project item, and selection container for the current selection  
        // If the selection spans multiple hierachies, hierarchyPtr is Zero  
        IVsMultiItemSelect multiItemSelect = null;  
        ErrorHandler.ThrowOnFailure(  
            monitorSelection.GetCurrentSelection(  
                out hierarchyPtr, out itemid,   
                out multiItemSelect, out selectionContainer));  
  
        // We only care if there is only one node selected in the tree  
        if (!(itemid == VSConstants.VSITEMID_NIL ||   
            hierarchyPtr == IntPtr.Zero ||  
            multiItemSelect != null ||  
            itemid == VSConstants.VSITEMID_SELECTION))  
        {  
            hierarchy = Marshal.GetObjectForIUnknown(hierarchyPtr)  
                as IVsHierarchy;  
        }  
    }  
    finally  
    {  
        if (hierarchyPtr != IntPtr.Zero)  
            Marshal.Release(hierarchyPtr);  
        if (selectionContainer != IntPtr.Zero)  
            Marshal.Release(selectionContainer);  
    }  
    ```  
  
2.  
  
### <a name="to-persist-the-selected-project-item-property-given-the-project-hierarchy"></a>프로젝트 계층 구조를 제공 합니다. 선택한 프로젝트 항목 속성을 유지 하려면  
  
1.  이전 절차에서 메서드에 지정 된 코드에 다음 코드를 추가 합니다.  
  
    ```  
    IVsBuildPropertyStorage buildPropertyStorage =   
        hierarchy as IVsBuildPropertyStorage;  
    if (buildPropertyStorage != null)  
    {  
        buildPropertyStorage.SetItemAttribute(itemId, "Author", "Tom");  
    }  
    ```  
  
### <a name="to-verify-that-the-property-is-persisted"></a>속성은 레코드가 있는지 확인 하려면  
  
1.  시작 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 및 다음 열거나 솔루션을 만듭니다.  
  
2.  프로젝트를 선택 항목에 VsPkg.cs **솔루션 탐색기**합니다.  
  
3.  중단점을 사용 하거나 VSPackage 로드 되 고 SetItemAttribute 실행 되는지 확인 합니다.  
  
    > [!NOTE]
    >  VSPackage는 UI 컨텍스트에서 autoload를 할 수 있습니다 <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionExists>합니다. 자세한 내용은 참조 [로드 Vspackage](../extensibility/loading-vspackages.md)합니다.  
  
4.  닫기 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 다음 메모장에서 프로젝트 파일을 엽니다. 표시 됩니다는 \<작성자 > 태그를 다음과 같이 Tom, 값:  
  
    ```  
    <Compile Include="VsPkg.cs">  
        <Author>Tom</Author>  
    </Compile>  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 도구](../extensibility/internals/custom-tools.md)