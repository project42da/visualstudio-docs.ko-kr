---
title: "GetAssemblyIdentity Task | Microsoft Docs"
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
  - "http://schemas.microsoft.com/developer/msbuild/2003#GetAssemblyIdentity"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MSBuild, GetAssemblyIdentity task"
  - "GetAssemblyIdentity task [MSBuild]"
ms.assetid: a977e072-37ad-4941-84a6-32a4483be55d
caps.latest.revision: 8
caps.handback.revision: 8
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# GetAssemblyIdentity Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지정한 파일에서 어셈블리 ID를 검색하고 ID 정보를 출력합니다.  
  
## 작업 매개 변수  
 다음 표에서는 `GetAssemblyIdentity` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`Assemblies`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 검색한 어셈블리 ID가 들어 있습니다.|  
|`AssemblyFiles`|필수적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> ID를 검색할 파일을 지정합니다.|  
  
## 설명  
 `Assemblies` 매개 변수에서 출력하는 항목에는 `Version`, `PublicKeyToken` 및 `Culture`라는 항목 메타데이터 엔트리가 들어 있습니다.  
  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `MyAssemblies` 항목으로 지정한 파일의 ID를 검색하고 그 결과를 `MyAssemblyIdentities` 항목에 출력합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyAssemblies Include="File1.dll;File2.dll" />  
    </ItemGroup>  
  
    <Target Name="RetrieveIdentities>  
        <GetAssemblyIdentity  
            AssemblyFiles="@(MyAssemblies)"  
            <Output  
                TaskParameter="Assemblies"  
                ItemName="MyAssemblyIdentities"  
    </Target>  
  
</Project>  
```  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)