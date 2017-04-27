---
title: "AssignProjectConfiguration 작업 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
ms.assetid: 09633a0b-8f6f-4aba-8058-7cb4d13ce2c0
caps.latest.revision: 7
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 7
---
# <a name="assignprojectconfiguration-task"></a>AssignProjectConfiguration 작업
이 작업은 목록 구성 문자열을 허용하고 여기에 지정된 프로젝트를 할당합니다.  
  
## <a name="task-parameters"></a>작업 매개 변수  
 다음 표에서는 `AssignProjectConfiguration` 작업의 매개 변수에 대해 설명합니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`SolutionConfigurationContents`|선택적 `string` 출력 매개 변수입니다.<br /><br /> 각 프로젝트에 대한 프로젝트 구성을 포함하는 XML 문자열을 포함합니다. 구성은 명명된 프로젝트에 할당됩니다.|  
|`DefaultToVcxPlatformMapping`|선택적 `string` 출력 매개 변수입니다.<br /><br /> 대부분의 형식에 사용된 플랫폼 이름에서 .vcxproj 파일에 사용된 이름으로의<br /><br /> 매핑 목록을 세미콜론으로 구분하여 포함합니다.<br /><br /> 예:<br /><br /> `"AnyCPU=Win32;X86=Win32;X64=X64"`|  
|`VcxToDefaultPlatformMapping`|Optional<br /><br /> `string` 출력 매개 변수입니다.<br /><br /> .vcxproj 플랫폼 이름에서 대부분의 형식에 사용되는 플랫폼 이름으로의 매핑 목록을 세미콜론으로 구분하여 포함합니다.<br /><br /> 예:<br /><br /> `"Win32=AnyCPU;X64=X64"`|  
|`CurrentProjectConfiguration`|선택적 `string` 출력 매개 변수입니다.<br /><br /> 현재 프로젝트에 대한 구성을 포함합니다.|  
|`CurrentProjectPlatform`|선택적 `string` 출력 매개 변수입니다.<br /><br /> 현재 프로젝트에 대한 플랫폼을 포함합니다.|  
|`OnlyReferenceAndBuildProjectsEnabledInSolutionConfiguration`|선택적 `bool` 출력 매개 변수입니다.<br /><br /> 프로젝트 구성에서 사용되지 않은 경우에도 참조를 빌드해야 함을 나타내는 플래그를 포함합니다.|  
|`ShouldUnsetParentConfigurationAndPlatform`|선택적 `bool` 출력 매개 변수입니다.<br /><br /> 부모 구성 및 플랫폼을 설정 해제해야 함을 나타나는 플래그를 포함합니다.|  
|`OutputType`|선택적 `string` 출력 매개 변수입니다.<br /><br /> 프로젝트에 대한 출력 형식을 포함합니다.|  
|`ResolveConfigurationPlatformUsingMappings`|선택적 `bool` 출력 매개 변수입니다.<br /><br /> 전달된 프로젝트 참조의 구성 및 플랫폼을 확인하기 위해 빌드가 기본 매핑을 사용해야 하는지를 나타내는 플래그를 포함합니다.|  
|`AssignedProjects`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 확인된 참조 경로의 목록을 포함합니다.|  
|`UnassignedProjects`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 사전 확인된 출력 목록을 사용하여 확인할 수 없는 프로젝트 참조 항목의 목록을 포함합니다.|  
  
## <a name="remarks"></a>설명  
 이 작업은 위에 나와 있는 매개 변수 외에 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다. 이 클래스는 <xref:Microsoft.Build.Utilities.Task> 클래스에서 매개 변수를 상속합니다. 이러한 추가 매개 변수 및 해당 설명이 포함된 목록은 [TaskExtension 기본 클래스](../msbuild/taskextension-base-class.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [작업 참조](../msbuild/msbuild-task-reference.md)


<!--HONumber=Feb17_HO4-->

