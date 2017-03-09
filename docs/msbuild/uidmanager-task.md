---
title: "UidManager Task | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "UidManager task [WPF MSBuild]"
  - "UidManager task [WPF MSBuild], parameters"
  - "managing UIDs when localizing XAML elements [WPF MSBuild]"
  - "localizing XAML elements [WPF MSBuild], managing UIDs"
  - "checking UIDs when localizing XAML elements [WPF MSBuild]"
ms.assetid: 4fc7b5a5-11b0-46ca-9656-8c2a0b08d1fe
caps.latest.revision: 5
caps.handback.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# UidManager Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

<xref:Microsoft.Build.Tasks.Windows.UidManager> 작업은 소스 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일에 포함된 모든 [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] 요소를 지역화하기 위해 UID\(고유 ID\)를 확인하거나, 업데이트하거나, 제거합니다.  
  
## 작업 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`IntermediateDirectory`|선택적 **String** 매개 변수입니다.<br /><br /> **MarkupFiles** 매개 변수로 지정된 소스 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일을 백업하는 데 사용되는 디렉터리를 지정합니다.|  
|`MarkupFiles`|필수 **ITaskItem\[\]** 매개 변수입니다.<br /><br /> UID 확인, 업데이트 또는 제거를 위해 포함할 소스 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일을 지정합니다.|  
|`Task`|필수 **String** 매개 변수입니다.<br /><br /> 수행할 UID 관리 작업을 지정합니다.  사용할 수 있는 옵션은 **Check**, **Update** 또는 **Remove**입니다.|  
  
## 예제  
 다음 예제에서는 <xref:Microsoft.Build.Tasks.Windows.UidManager> 작업을 사용하여 지정한 소스 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일에 UID가 적절한 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 요소가 포함되어 있는지 확인합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.UidManager"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="UidManagerTask">  
    <UidManager  
      Task="Check"  
      MarkupFiles="Page1.xaml;Page2.xaml"  
      IntermediateDirectory="c:\UidManagerIntermediateDirectory" />  
  </Target>  
</Project>  
```  
  
## 참고 항목  
 [WPF MSBuild Reference](../msbuild/wpf-msbuild-reference.md)   
 [Task Reference](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild Reference](../msbuild/msbuild-reference.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)   
 [WPF 응용 프로그램 만들기\(WPF\)](../Topic/Building%20a%20WPF%20Application%20\(WPF\).md)   
 [방법: 응용 프로그램 지역화](../Topic/How%20to:%20Localize%20an%20Application.md)