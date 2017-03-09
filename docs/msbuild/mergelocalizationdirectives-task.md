---
title: "MergeLocalizationDirectives Task | Microsoft Docs"
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
  - "localizing XAML [WPF MSBuild], moving comments and attributes to a separate file"
  - "MergeLocalizationDirectives task [WPF MSBuild], parameters"
  - "MergeLocalizationDirectives task [WPF MSBuild]"
  - "moving localization comments and attributes to a separate file [WPF MSBuild]"
ms.assetid: 9095b4f1-88da-4194-914b-ee1456826830
caps.latest.revision: 5
caps.handback.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# MergeLocalizationDirectives Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

<xref:Microsoft.Build.Tasks.Windows.MergeLocalizationDirectives> 작업에서는 하나 이상의 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 이진 형식 파일의 지역화 특성 및 주석을 전체 어셈블리에 대한 단일 파일로 병합합니다.  
  
## 작업 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`GeneratedLocalizationFiles`|필수 **ITaskItem\[\]** 매개 변수입니다.<br /><br /> 개별 파일에 대한 지역화 지시문 파일의 목록을 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 이진 형식으로 지정합니다.|  
|`OutputFile`|필수 **String** 출력 매개 변수입니다.<br /><br /> 컴파일된 지역화 지시문 어셈블리의 출력 경로를 지정합니다.|  
  
## 설명  
 [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] 콘텐츠에 지역화 특성 및 주석을 추가할 수 있습니다.  [!INCLUDE[TLA#tla_wpf](../msbuild/includes/tlasharptla_wpf_md.md)] 지역화 지원을 통해 지역화 특성 및 주석을 제거하고, 생성된 어셈블리와 별개인 .loc 파일에 넣을 수 있습니다.  이렇게 하려면 **LocalizationPropertyStorage** 특성을 사용합니다.  지역화 특성과 주석 및 **LocalizationPropertyStorage**에 대한 자세한 내용은 [지역화 특성 및 주석](../Topic/Localization%20Attributes%20and%20Comments.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 이진 형식 파일 몇 개의 지역화 주석을 하나의 .loc 파일로 병합합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.MergeLocalizationDirectives"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="MergeLocalizationDirectivesTask">  
    <MergeLocalizationDirectives   
      GeneratedLocalizationFiles="obj\debug\page1.loc;obj\debug\page2.loc;obj\debug\page3.loc"  
      OutputFile="obj\debug\WPFMSBuildSample.loc" />  
  </Target>  
</Project>  
```  
  
## 참고 항목  
 [WPF MSBuild Reference](../msbuild/wpf-msbuild-reference.md)   
 [Task Reference](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild Reference](../msbuild/msbuild-reference.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)   
 [WPF 응용 프로그램 만들기\(WPF\)](../Topic/Building%20a%20WPF%20Application%20\(WPF\).md)