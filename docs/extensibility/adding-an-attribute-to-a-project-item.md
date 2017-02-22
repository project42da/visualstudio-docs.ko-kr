---
title: "프로젝트 항목에 특성 추가 | Microsoft Docs"
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
  - "프로젝트 항목에 추가 하는 특성 [Visual Studio]"
ms.assetid: 404a71d5-cce5-44e7-9eaf-d747c794fedb
caps.latest.revision: 4
caps.handback.revision: 4
ms.author: "gregvanl"
manager: "ghogen"
---
# 프로젝트 항목에 특성 추가
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

메서드 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.GetItemAttribute%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetItemAttribute%2A> get 및 프로젝트 항목의 속성 값을 설정 합니다.  아직 존재 하지 않을 경우 SetItemAttribute 프로젝트 항목 메타 데이터를 추가 하는 특성을 만듭니다.  
  
## 특성에 대 한 프로젝트 항목 추가  
  
#### 특성에 대 한 프로젝트 항목을 추가 하려면  
  
-   다음 코드를 사용 하는 <xref:EnvDTE.DTE> 자동화 개체 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetItemAttribute%2A> 메서드 특성에 대 한 프로젝트 항목을 추가 하려면.  프로젝트 항목 이름 "program.cs"에서 프로젝트 항목 ID는 가져옵니다.  특성 "MyAttribute" 이며이 프로젝트 항목을 추가 "MyValue" 값이 지정 됩니다.  
  
    ```  
    EnvDTE.DTE dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));  
    EnvDTE.Project project = dte.Solution.Projects.Item(1);  
  
    string uniqueName = project.UniqueName;  
    IVsSolution solution =     (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));  
    IVsHierarchy hierarchy;  
    solution.GetProjectOfUniqueName(uniqueName, out hierarchy);  
    IVsBuildPropertyStorage buildPropertyStorage = hierarchy as IVsBuildPropertyStorage;  
    if (buildPropertyStorage != null)  
    {  
        uint itemId;  
        string fullPath =         (string)project.ProjectItems.Item("Program.cs").Properties.Item("FullPath").Value;  
        hierarchy.ParseCanonicalName(fullPath, out itemId);  
        buildPropertyStorage.SetItemAttribute(  
            itemId, "MyAttribute", "MyValue");  
    }  
  
    ```  
  
## 참고 항목  
 [MSBuild 프로젝트 파일에 데이터를 유지](../extensibility/internals/persisting-data-in-the-msbuild-project-file.md)