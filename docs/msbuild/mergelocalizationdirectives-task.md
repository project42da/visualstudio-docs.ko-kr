---
title: "MergeLocalizationDirectives 작업 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- localizing XAML [WPF MSBuild], moving comments and attributes to a separate file
- MergeLocalizationDirectives task [WPF MSBuild], parameters
- MergeLocalizationDirectives task [WPF MSBuild]
- moving localization comments and attributes to a separate file [WPF MSBuild]
ms.assetid: 9095b4f1-88da-4194-914b-ee1456826830
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b8e53bcb94c753659848b336be243a2c582fc0c2
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="mergelocalizationdirectives-task"></a>MergeLocalizationDirectives 작업
<xref:Microsoft.Build.Tasks.Windows.MergeLocalizationDirectives> 작업은 하나 이상의 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 이진 형식 파일에 대한 지역화 특성과 주석을 전체 어셈블리에 대한 단일 파일로 병합합니다.  
  
## <a name="task-parameters"></a>작업 매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`GeneratedLocalizationFiles`|필수 **ITaskItem[]** 매개 변수입니다.<br /><br /> 개별 파일에 대한 지역화 지시문 파일 목록을 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 이진 형식으로 지정합니다.|  
|`OutputFile`|필수 **String** 출력 매개 변수입니다.<br /><br /> 컴파일된 지역화 지시문 어셈블리의 출력 경로를 지정합니다.|  
  
## <a name="remarks"></a>설명  
 지역화 특성 및 주석을 [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] 내용에 추가할 수 있습니다. [!INCLUDE[TLA#tla_wpf](../msbuild/includes/tlasharptla_wpf_md.md)] 지역화 지원을 사용하면 지역화 특성 및 주석을 제거하고 생성된 어셈블리와는 별개인 .loc 파일에 추가할 수 있습니다. 이 작업은 **LocalizationPropertyStorage** 특성을 사용하여 수행할 수 있습니다. 지역화 특성 및 주석과 **LocalizationPropertyStorage**에 대한 자세한 내용은 [지역화 특성 및 주석](/dotnet/framework/wpf/advanced/localization-attributes-and-comments)을 참조하세요.  
  
## <a name="example"></a>예  
 다음 예제에서는 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 이진 형식 파일에 해당하는 지역화 주석을 단일 .loc 파일에 병합합니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 [WPF MSBuild 참조](../msbuild/wpf-msbuild-reference.md)   
 [작업 참조](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild 참조](../msbuild/msbuild-reference.md)   
 [작업 참조](../msbuild/msbuild-task-reference.md)   
 [WPF 응용 프로그램 빌드(WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)