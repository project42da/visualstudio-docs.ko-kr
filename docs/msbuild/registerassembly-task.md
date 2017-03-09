---
title: "RegisterAssembly Task | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#RegisterAssembly"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MSBuild, RegisterAssembly task"
  - "RegisterAssembly task [MSBuild]"
ms.assetid: ba5f19ac-6764-4d28-9b79-a86de58f8987
caps.latest.revision: 16
caps.handback.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# RegisterAssembly Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지정된 어셈블리 내의 메타데이터를 읽고 필요한 엔트리를 레지스트리에 추가합니다. 이렇게 하면 COM 클라이언트에서 투명하게 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 클래스를 만들 수 있습니다.  이 작업의 동작은 [Regasm.exe\(어셈블리 등록 도구\)](../Topic/Regasm.exe%20\(Assembly%20Registration%20Tool\).md)의 동작과 비슷하지만 몇 가지 차이가 있습니다.  
  
## 매개 변수  
 다음 표에서는 `RegisterAssembly` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`Assemblies`|필수적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> COM을 사용하여 등록할 어셈블리를 지정합니다.|  
|`AssemblyListFile`|선택적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> `RegisterAssembly` 작업과 [UnregisterAssembly](../msbuild/unregisterassembly-task.md) 작업 사이의 상태에 대한 정보가 있습니다.  이 매개 변수는 `UnregisterAssembly` 작업이 `RegisterAssembly` 작업 등록에 실패한 어셈블리의 등록을 취소하지 못하게 합니다.|  
|`CreateCodeBase`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 전역 어셈블리 캐시에 설치되지 않은 어셈블리에 대한 파일 경로를 지정하는 코드베이스 엔트리를 레지스트리에 만듭니다.  전역 어셈블리 캐시에 등록 중인 어셈블리를 다음에 설치하려면 이 옵션을 지정해야 합니다.|  
|`TypeLibFiles`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 지정된 어셈블리에서 생성할 형식 라이브러리를 지정합니다.  생성된 형식 라이브러리에는 어셈블리 내에서 정의한 액세스 가능한 형식의 정의가 포함됩니다.  형식 라이브러리는 다음과 같은 조건 중 하나가 충족되는 경우에만 생성됩니다.<br /><br /> -   해당 이름의 형식 라이브러리가 해당 위치에 없는 경우<br />-   형식 라이브러리가 있지만 어셈블리에서 전달하려는 것보다 오래된 경우<br /><br /> 형식 라이브러리가 어셈블리에서 전달하려는 것보다 최신 버전이면 새 라이브러리가 작성되지 않지만 어셈블리는 등록됩니다.<br /><br /> 이 매개 변수를 지정한 경우 항목의 수는 `Assemblies` 매개 변수와 동일해야 합니다. 그렇지 않으면 작업이 실패합니다.  입력을 지정하지 않으면 작업이 어셈블리의 이름으로 기본 설정되고 항목의 확장명이 .tlb로 변경됩니다.|  
  
## 설명  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `MyAssemblies` 항목 컬렉션에서 지정한 어셈블리를 등록하기 위해 `RegisterAssembly` 작업을 사용합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyAssemblies Include="MyAssembly.dll" />  
    <ItemGroup>  
  
    <Target Name="RegisterAssemblies">  
        <RegisterAssembly  
            Assemblies="@(MyAssemblies)" >  
    </Target>  
  
</Project>  
```  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)