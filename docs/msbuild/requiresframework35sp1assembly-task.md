---
title: "RequiresFramework35SP1Assembly Task | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "RequiresFramework35SP1Assembly task [MSBuild]"
  - "MSBuild, RequiresFramework35SP1Assembly task"
ms.assetid: 755c018a-8a8b-4c94-8aee-3f171fc419e5
caps.latest.revision: 6
caps.handback.revision: 6
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# RequiresFramework35SP1Assembly Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

응용 프로그램에 .NET Framework 3.5 SP1이 필요한지 여부를 확인합니다.  
  
## 매개 변수  
 다음 표에서는 `RequiresFramework35SP1Assembly` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`Assemblies`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 응용 프로그램에서 참조 되는 어셈블리를 지정 합니다.|  
|`CreateDesktopShortcut`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 설치 중 바탕 화면에 바로 가기 아이콘을 만듭니다.|  
|`DeploymentManifestEntryPoint`|선택적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> 응용 프로그램의 매니페스트 파일 이름을 지정합니다.|  
|`EntryPoint`|선택적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> 응용 프로그램이 실행될 때 실행해야 할 어셈블리를 가져오거나 지정합니다.|  
|`ErrorReportUrl`|선택적 `String` 매개 변수입니다.<br /><br /> ClickOnce 설치 중 보게 되는 대화 상자에 표시되는 웹 사이트를 지정합니다.|  
|`Files`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 응용 프로그램을 게시할 때 배치할 파일의 목록을 지정합니다.|  
|`ReferencedAssemblies`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 프로젝트에서 참조 되는 어셈블리를 지정 합니다.|  
|`RequiresMinimumFramework35SP1`|선택적 `Boolean` 출력 매개 변수입니다.<br /><br /> `true`인 경우 응용 프로그램에 .NET Framework 3.5 SP1이 필요합니다.|  
|`SigningManifests`|선택적 `Boolean` 출력 매개 변수입니다.<br /><br /> `true`인 경우 ClickOnce 매니페스트가 서명됩니다.|  
|`SuiteName`|선택적 `String` 매개 변수입니다.<br /><br /> **시작** 메뉴에서 응용 프로그램을 설치할 폴더 이름을 지정합니다.|  
|`TargetFrameworkVersion`|선택적 `String` 매개 변수입니다.<br /><br /> 이 응용 프로그램의 대상이 되는 .NET Framework의 버전을 지정합니다.|  
  
## 설명  
 이 표에 나열된 매개 변수를 갖는 것 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)