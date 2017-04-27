---
title: "ResourcesGenerator 작업 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- embedding resources into a .resources file [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild], parameters
ms.assetid: e782bbac-9ee6-472b-8171-3ee008c77b4e
caps.latest.revision: 6
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 79460291e91f0659df0a4241e17616e55187a0e2
ms.openlocfilehash: a698aec32ff5ec093fe2cff2dc0533f6e364be21
ms.lasthandoff: 02/22/2017

---
# <a name="resourcesgenerator-task"></a>ResourcesGenerator 작업
<xref:Microsoft.Build.Tasks.Windows.ResourcesGenerator> 작업은 하나 이상의 리소스(이진 형식 및 기타 확장 형식의 .jpg,.ico,.bmp, [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)])를 .resources 파일에 포함합니다.  
  
## <a name="task-parameters"></a>작업 매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`OutputPath`|필수 **String** 매개 변수입니다.<br /><br /> 출력 디렉터리의 경로를 지정합니다. 경로가 절대 경로가 아니면 루트 프로젝트 디렉터리의 상대 경로로 처리됩니다.|  
|`OutputResourcesFile`|필수 **ITaskItem** 출력 매개 변수입니다.<br /><br /> 생성된 .resources 파일의 경로 및 이름을 지정합니다. 경로가 절대 경로가 아니면 루트 프로젝트 디렉터리에 상대적으로 .resource 파일이 생성됩니다.|  
|`ResourcesFiles`|필수 **ITaskItem[]** 매개 변수입니다.<br /><br /> 생성된 .resources 파일에 포함할 하나 이상의 리소스를 지정합니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 단일 .bmp 리소스로 .resources 파일을 생성합니다. .bmp 리소스는 프로젝트 루트 디렉터리에 상대적인 디렉터리에 생성됩니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 [WPF MSBuild 참조](../msbuild/wpf-msbuild-reference.md)   
 [작업 참조](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild 참조](../msbuild/msbuild-reference.md)   
 [작업 참조](../msbuild/msbuild-task-reference.md)   
 [WPF 응용 프로그램 빌드(WPF)](http://msdn.microsoft.com/Library/a58696fd-bdad-4b55-9759-136dfdf8b91c)