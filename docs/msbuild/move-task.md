---
title: "Move Task | Microsoft Docs"
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
  - "MSBuild, Move task"
  - "Move task [MSBuild]"
ms.assetid: d1405347-1309-4f18-b565-905408093d59
caps.latest.revision: 4
caps.handback.revision: 4
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# Move Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

파일을 새 위치로 이동합니다.  
  
## 매개 변수  
 다음 표에서는 `Move` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`DestinationFiles`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 소스 파일을 이동할 대상이 될 파일 목록을 지정합니다.  이 목록은 `SourceFiles` 매개 변수에서 지정한 목록과 일대일로 매핑되어야 합니다.  즉, `SourceFiles`에서 지정한 첫 번째 파일은 `DestinationFiles`에서 지정한 첫 번째 위치로 이동됩니다.|  
|`DestinationFolder`|선택적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> 파일을 이동할 대상이 될 디렉터리를 지정합니다.|  
|`MovedFiles`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 성공적으로 이동한 항목이 들어 있습니다.|  
|`OverwriteReadOnlyFiles`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 읽기 전용 파일로 표시되어 있는 경우에도 파일을 덮어씁니다.|  
|`SourceFiles`|필수적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 이동할 파일을 지정합니다.|  
  
## 설명  
 `DestinationFolder` 매개 변수 또는 `DestinationFiles` 매개 변수를 지정해야 합니다.  두 매개 변수를 모두 지정하면 작업이 실패하고 오류가 기록됩니다.  
  
 이 표에 나열된 매개 변수를 갖는 것 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)