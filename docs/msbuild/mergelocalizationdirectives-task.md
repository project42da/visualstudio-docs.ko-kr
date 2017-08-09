---
title: "MergeLocalizationDirectives 작업 | Microsoft Docs"
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
- localizing XAML [WPF MSBuild], moving comments and attributes to a separate file
- MergeLocalizationDirectives task [WPF MSBuild], parameters
- MergeLocalizationDirectives task [WPF MSBuild]
- moving localization comments and attributes to a separate file [WPF MSBuild]
ms.assetid: 9095b4f1-88da-4194-914b-ee1456826830
caps.latest.revision: 5
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 3d32d11a430227800cb3ed53831a9565eb6adeb3
ms.openlocfilehash: e56ad5826bd6d18bd4409e98f8d54c49d266af82
ms.contentlocale: ko-kr
ms.lasthandoff: 05/30/2017

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
  
## <a name="example"></a>예제  
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
