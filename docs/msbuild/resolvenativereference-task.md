---
title: "ResolveNativeReference 작업 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ResolveNativeReference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, ResolveNativeReference task
- ResolveNativeReference task [MSBuild]
ms.assetid: 56acd101-de77-4eec-92c6-f5c6d2187579
caps.latest.revision: 9
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
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: b0b08a9602c81e504bf2cd01d1d1ce9720dc6b2a
ms.lasthandoff: 02/22/2017

---
# <a name="resolvenativereference-task"></a>ResolveNativeReference 작업
네이티브 참조를 확인합니다. <xref:Microsoft.Build.Tasks.ResolveNativeReference> 클래스를 구현합니다. 이 클래스는 코드에서 직접 사용할 수 없는 .NET Framework 인프라를 지원합니다.  
  
## <a name="task-parameters"></a>작업 매개 변수  
 다음 표에서는 `ResolveNativeReference` 작업의 매개 변수에 대해 설명합니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`AdditionalSearchPaths`|필수 [String](assetId:///String?qualifyHint=False&autoUpgrade=True)`[]` 매개 변수입니다.<br /><br /> 네이티브 참조의 어셈블리 ID를 확인하기 위한 검색 경로를 가져오거나 설정합니다.|  
|`ContainedComComponents`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 네이티브 어셈블리의 COM 구성 요소를 가져오거나 설정합니다.|  
|`ContainedLooseEtcFiles`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 네이티브 매니페스트에 나열된 느슨한 Etc 파일을 가져오거나 설정합니다.|  
|`ContainedLooseTlbFiles`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 네이티브 어셈블리의 느슨한 .tlb 파일을 가져오거나 설정합니다.|  
|`ContainedPrerequisiteAssemblies`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 매니페스트를 사용하기 위해 있어야 하는 어셈블리를 가져오거나 설정합니다.|  
|`ContainedTypeLibraries`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 네이티브 어셈블리의 형식 라이브러리를 가져오거나 설정합니다.|  
|`ContainingReferenceFiles`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 참조 파일을 가져오거나 설정합니다.|  
|`NativeReferences`|필수 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> Win32 네이티브 어셈블리 참조를 가져오거나 설정합니다.|  
  
## <a name="remarks"></a>설명  
 이 작업은 위에 나와 있는 매개 변수 외에 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다. 이 클래스는 <xref:Microsoft.Build.Utilities.Task> 클래스에서 매개 변수를 상속합니다. 이러한 추가 매개 변수 및 해당 설명이 포함된 목록은 [TaskExtension 기본 클래스](../msbuild/taskextension-base-class.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [작업 참조](../msbuild/msbuild-task-reference.md)