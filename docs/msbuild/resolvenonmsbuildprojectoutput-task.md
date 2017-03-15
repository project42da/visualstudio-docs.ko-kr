---
title: "ResolveNonMSBuildProjectOutput Task | Microsoft Docs"
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
helpviewer_keywords: 
  - "MSBuild, ResolveNonMSBuildProjectOutput task"
  - "ResolveNonMSBuildProjectOutput task [MSBuild]"
ms.assetid: a0b8fcec-8c8d-4867-85ac-5304c5108e5e
caps.latest.revision: 4
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 4
---
# ResolveNonMSBuildProjectOutput Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

비 MSBuild 프로젝트 참조용 출력 파일을 확인합니다.  
  
## 매개 변수  
 다음 표에서는 `ResolveNonMSBuildProjectOutput` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`PreresolvedProjectOutputs`|선택적 `String` 매개 변수입니다.<br /><br /> 확인된 프로젝트 출력을 포함하는 XML 문자열을 지정합니다.|  
|`ProjectReferences`|필수적 <xref:Microsoft.Build.Framework.ITaskItem>`[]`  매개 변수입니다.<br /><br /> 프로젝트 참조를 지정합니다.|  
|`ResolvedOutputPaths`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 확인된 참조 경로의 목록을 포함합니다\(원래의 프로젝트 참조 특성 유지\).|  
|`UnresolvedProjectReferences`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 사전 확인된 결과 목록을 사용하여 확인할 수 없는 프로젝트 참조 항목 목록을 포함합니다.<br /><br /> Visual Studio는 MSBuild가 아닌 프로젝트만을 사전 확인하므로 이는 이 목록의 프로젝트 참조가 MSBuild 형식임을 의미합니다.|  
  
## 설명  
 이 표에 나열된 매개 변수를 갖는 것 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)