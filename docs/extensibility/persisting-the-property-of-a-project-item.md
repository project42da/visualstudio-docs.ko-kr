---
title: "프로젝트 항목의 속성을 유지 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 항목에 추가 속성"
  - "프로젝트 항목 속성 추가"
ms.assetid: d7a0f2b0-d427-4d49-9536-54edfb37c0f3
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# 프로젝트 항목의 속성을 유지
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

소스 파일의 작성자와 같은 프로젝트 항목에 추가 하는 속성을 유지할 수도 있습니다. 이렇게 하려면 프로젝트 파일에서 속성을 저장 합니다.  
  
 프로젝트 파일에서 속성을 유지 하는 첫 번째 단계는 파일로 프로젝트의 계층 구조를 얻을 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 인터페이스입니다. 자동화를 사용 하거나 사용 하 여이 인터페이스를 가져올 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>합니다. 인터페이스를 가져온 후에 현재 선택한 프로젝트 항목을 확인 하려면 사용할 수 있습니다. 프로젝트 항목 ID가 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetItemAttribute%2A> 는 속성을 추가 합니다.  
  
 VsPkg.cs 속성을 유지 하는 다음 절차에서 `Author` 값을 가진 `Tom` 프로젝트 파일에 있습니다.  
  
### DTE 개체와 프로젝트 계층 구조를 가져오려면  
  
1.  VSPackage에 다음 코드를 추가 합니다.  
  
    ```c#  
    EnvDTE.DTE dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE)); EnvDTE.Project project = dte.Solution.Projects.Item(1); string uniqueName = project.UniqueName; IVsSolution solution = (IVsSolution)Package.GetGlobalService(typeof(SVsSolution)); IVsHierarchy hierarchy; solution.GetProjectOfUniqueName(uniqueName, out hierarchy);  
    ```  
  
### DTE 개체와 프로젝트 항목 속성을 유지 하려면  
  
1.  이전 절차에서 메서드에 제공 된 코드에 다음 코드를 추가 합니다.  
  
    ```c#  
    IVsBuildPropertyStorage buildPropertyStorage = hierarchy as IVsBuildPropertyStorage; if (buildPropertyStorage != null) { uint itemId; string fullPath = (string)project.ProjectItems.Item( "VsPkg.cs").Properties.Item("FullPath").Value; hierarchy.ParseCanonicalName(fullPath, out itemId); buildPropertyStorage.SetItemAttribute(itemId, "Author", "Tom"); }  
    ```  
  
### IVsMonitorSelection를 사용 하 여 프로젝트 계층 구조를 가져오려면  
  
1.  VSPackage에 다음 코드를 추가 합니다.  
  
    ```c#  
    IVsHierarchy hierarchy = null; IntPtr hierarchyPtr = IntPtr.Zero; IntPtr selectionContainer = IntPtr.Zero; uint itemid; // Retrieve shell interface in order to get current selection IVsMonitorSelection monitorSelection =     Package.GetGlobalService(typeof(SVsShellMonitorSelection)) as     IVsMonitorSelection; if (monitorSelection == null) throw new InvalidOperationException(); try { // Get the current project hierarchy, project item, and selection container for the current selection // If the selection spans multiple hierachies, hierarchyPtr is Zero IVsMultiItemSelect multiItemSelect = null; ErrorHandler.ThrowOnFailure( monitorSelection.GetCurrentSelection( out hierarchyPtr, out itemid, out multiItemSelect, out selectionContainer)); // We only care if there is only one node selected in the tree if (!(itemid == VSConstants.VSITEMID_NIL || hierarchyPtr == IntPtr.Zero || multiItemSelect != null || itemid == VSConstants.VSITEMID_SELECTION)) { hierarchy = Marshal.GetObjectForIUnknown(hierarchyPtr) as IVsHierarchy; } } finally { if (hierarchyPtr != IntPtr.Zero) Marshal.Release(hierarchyPtr); if (selectionContainer != IntPtr.Zero) Marshal.Release(selectionContainer); }  
    ```  
  
2.  
  
### 프로젝트 계층 구조에 선택한 프로젝트 항목 속성을 유지 하려면  
  
1.  이전 절차에서 메서드에 제공 된 코드에 다음 코드를 추가 합니다.  
  
    ```  
    IVsBuildPropertyStorage buildPropertyStorage = hierarchy as IVsBuildPropertyStorage; if (buildPropertyStorage != null) { buildPropertyStorage.SetItemAttribute(itemId, "Author", "Tom"); }  
    ```  
  
### 속성은 유지 되는지 확인 하려면  
  
1.  시작 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 하 고 다음 열거나 솔루션을 만듭니다.  
  
2.  프로젝트 선택 항목에 VsPkg.cs **솔루션 탐색기**합니다.  
  
3.  중단점을 사용 하거나 그렇지 않으면 VSPackage 로드 되 고 SetItemAttribute 실행 되는지 결정 합니다.  
  
    > [!NOTE]
    >  자동 로드 UI 컨텍스트에서 VSPackage를 할 수 있습니다 <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionExists>합니다. 자세한 내용은 [Vspackage를 로드합니다.](../extensibility/loading-vspackages.md)을 참조하십시오.  
  
4.  닫기 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 다음 메모장에서 프로젝트 파일을 엽니다. Tom 값을 가진 \< 작성자 \> 태그를 다음과 같이 표시 됩니다.  
  
    ```  
    <Compile Include="VsPkg.cs"> <Author>Tom</Author> </Compile>  
    ```  
  
## 참고 항목  
 [사용자 지정 도구](../extensibility/internals/custom-tools.md)