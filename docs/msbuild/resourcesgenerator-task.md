---
title: "ResourcesGenerator Task | Microsoft Docs"
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
  - "embedding resources into a .resources file [WPF MSBuild]"
  - "ResourcesGenerator task [WPF MSBuild]"
  - "ResourcesGenerator task [WPF MSBuild], parameters"
ms.assetid: e782bbac-9ee6-472b-8171-3ee008c77b4e
caps.latest.revision: 6
caps.handback.revision: 6
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# ResourcesGenerator Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

<xref:Microsoft.Build.Tasks.Windows.ResourcesGenerator> 작업에서는 하나 이상의 리소스\(이진 형식의 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)], .jpg, .ico, .bmp 및 기타 확장 형식\)를 .resources 파일에 포함합니다.  
  
## 작업 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`OutputPath`|필수 **String** 매개 변수입니다.<br /><br /> 출력 디렉터리의 경로를 지정합니다.  경로가 절대 경로가 아닌 경우에는 루트 프로젝트 디렉터리에 대한 상대 경로로 간주됩니다.|  
|`OutputResourcesFile`|필수 **ITaskItem\[\]** 출력 매개 변수입니다.<br /><br /> 생성되는 .resources 파일의 경로와 이름을 지정합니다.  경로가 절대 경로가 아닌 경우 .resources 파일은 루트 프로젝트 디렉터리에 대한 상대 경로에 생성됩니다.|  
|`ResourcesFiles`|필수 **ITaskItem\[\]** 매개 변수입니다.<br /><br /> 생성되는 .resources 파일에 포함할 하나 이상의 리소스를 지정합니다.|  
  
## 예제  
 다음 예제에서는 하나의 .bmp 리소스가 있는 .resources 파일을 생성합니다.  .bmp 리소스는 프로젝트 루트 디렉터리에 대해 상대적인 디렉터리에 생성됩니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.ResourcesGenerator"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="ResourcesGeneratorTask">  
    <ResourcesGenerator  
      ResourceFiles="Resource1.bmp"  
      OutputPath="myresources"  
      OutputResourcesFile="myresources\my.resources" />  
  </Target>  
</Project>  
```  
  
## 참고 항목  
 [WPF MSBuild Reference](../msbuild/wpf-msbuild-reference.md)   
 [Task Reference](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild Reference](../msbuild/msbuild-reference.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)   
 [WPF 응용 프로그램 만들기\(WPF\)](../Topic/Building%20a%20WPF%20Application%20\(WPF\).md)