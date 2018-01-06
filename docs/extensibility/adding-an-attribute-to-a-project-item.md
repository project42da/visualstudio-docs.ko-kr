---
title: "프로젝트 항목에 특성 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: attributes [Visual Studio], adding to a project item
ms.assetid: 404a71d5-cce5-44e7-9eaf-d747c794fedb
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 011c6dbf74f12921b0458db9990b9f1e0e807c48
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="adding-an-attribute-to-a-project-item"></a>프로젝트 항목에 특성 추가
메서드 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.GetItemAttribute%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetItemAttribute%2A> 가져오고 프로젝트 항목의 특성 값을 설정 합니다. SetItemAttribute 특성을 만듭니다는 이미 존재 하지 않는 경우 프로젝트의 항목 메타 데이터에 추가 합니다.  
  
## <a name="adding-an-attribute-to-a-project-item"></a>프로젝트 항목에 특성 추가  
  
#### <a name="to-add-an-attribute-to-a-project-item"></a>프로젝트 항목에 특성을 추가 하려면  
  
-   다음 코드에서는 <xref:EnvDTE.DTE> 자동화 개체와 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetItemAttribute%2A> 메서드를 프로젝트 항목에 특성을 추가 합니다. 프로젝트 항목 ID는 프로젝트 항목 이름 "program.cs"에서 가져옵니다. 특성 "MyAttribute"이 프로젝트 항목에 추가 되 고 "MyValue" 값이 지정 됩니다.  
  
    ```  
    EnvDTE.DTE dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));  
    EnvDTE.Project project = dte.Solution.Projects.Item(1);  
  
    string uniqueName = project.UniqueName;  
    IVsSolution solution =     (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));  
    IVsHierarchy hierarchy;  
    solution.GetProjectOfUniqueName(uniqueName, out hierarchy);  
    IVsBuildPropertyStorage buildPropertyStorage = hierarchy as IVsBuildPropertyStorage;  
    if (buildPropertyStorage != null)  
    {  
        uint itemId;  
        string fullPath =         (string)project.ProjectItems.Item("Program.cs").Properties.Item("FullPath").Value;  
        hierarchy.ParseCanonicalName(fullPath, out itemId);  
        buildPropertyStorage.SetItemAttribute(  
            itemId, "MyAttribute", "MyValue");  
    }  
  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [MSBuild 프로젝트 파일의 데이터 유지](../extensibility/internals/persisting-data-in-the-msbuild-project-file.md)