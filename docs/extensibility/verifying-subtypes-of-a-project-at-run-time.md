---
title: "런타임 시 프로젝트의 하위 형식 확인 | Microsoft Docs"
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
  - "프로젝트 하위 형식"
  - "하위 형식 확인"
ms.assetid: b87780ec-36a3-4e9a-9ee2-7abdc26db739
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# 런타임 시 프로젝트의 하위 형식 확인
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSPackage를 사용자 지정 프로젝트 하위 형식에 따라 달라 집니다 찾으려는 하위 요소가 없는 경우 안정적으로 실패할 수 있도록 하위 형식 하는 논리를 포함 해야 합니다. 다음 절차에는 지정 된 하위의 존재를 확인 하는 방법을 보여 줍니다.  
  
### 하위 형식의 존재를 확인 하려면  
  
1.  로 프로젝트 및 솔루션 개체에서 프로젝트 계층 구조를 가져올는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> VSPackage에 다음 코드를 추가 하 여 개체입니다.  
  
    ```  
    EnvDTE.DTE dte;  
    dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));  
  
    EnvDTE.Project project;  
    project = dte.Solution.Projects.Item(1);  
  
    IVsSolution solution;  
    solution = (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));  
  
    IVsHierarchy hierarchy;  
    hierarchy = solution.GetProjectOfUniqueName(project.UniqueName);  
  
    ```  
  
2.  계층 구조를 캐스팅은 <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected> 인터페이스입니다.  
  
    ```  
    IVsAggregatableProjectCorrected AP;  
    AP = hierarchy as IVsAggregatableProjectCorrected;  
  
    ```  
  
3.  호출 하 여 프로젝트 형식 Guid 목록을 가져올는 <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected.GetAggregateProjectTypeGuids%2A>합니다.  
  
    ```  
    string projTypeGuids = AP.GetAggregateProjectTypeGuids().ToUpper();  
  
    ```  
  
4.  지정 된 하위 유형의 GUID 목록을 확인 합니다.  
  
    ```  
    // Replace the string "MyGUID" with the GUID of the subtype.  
    string guidMySubtype = "MyGUID";  
    if (projTypeGuids.IndexOf(guidMySubtype) > 0)  
    {  
        // The specified subtype is present.  
    }  
    ```  
  
## 참고 항목  
 [프로젝트 하위 형식](../extensibility/internals/project-subtypes.md)   
 [프로젝트 하위 형식 디자인](../extensibility/internals/project-subtypes-design.md)   
 [속성 및 프로젝트 하위 형식에 의해 확장 메서드](../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md)