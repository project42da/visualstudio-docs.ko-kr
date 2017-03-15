---
title: "WriteCodeFragment Task | Microsoft Docs"
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
  - "MSBuild, WriteCodeFragment task"
  - "WriteCodeFragment task [MSBuild]"
ms.assetid: 1d2514b4-5bef-43bb-bebe-496da8ef063c
caps.latest.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 5
---
# WriteCodeFragment Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지정 된 생성 되는 코드 조각에서 임시 코드 파일을 생성합니다.  파일을 삭제하지 않습니다.  
  
## 매개 변수  
 다음 표에서는 `WriteCodeFragment` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`AssemblyAttributes`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 쓸 특성에 대한 설명입니다.  `Include` 항목 값은 속성의 전체 형식 이름입니다\(예: "System.AssemblyVersionAttribute"\).<br /><br /> 각 메타데이터는 매개 변수의 이름\-값 쌍이며 `String` 형식이어야 합니다.  일부 특성만 위치 생성자 인수를 허용합니다.  그러나 모든 속성에서 그러한 인수를 사용할 수 있습니다.  위치 생성자 특성을 설정하려면 "\_Parameter1", "\_Parameter2" 등과 같은 메타데이터 이름을 사용합니다.<br /><br /> 매개 변수 인덱스는 생략할 수 없습니다.|  
|`Language`|필수적 `String` 매개 변수입니다.<br /><br /> 생성할 코드의 언어를 지정합니다.<br /><br /> `Language`는 CodeDom 공급자를 사용할 수 있는 모든 언어가 될 수 있습니다\(예: "C\#" 또는 "VisualBasic"\).  내보낸 파일에는 해당 언어의 기본 파일 확장명이 지정됩니다.|  
|`OutputDirectory`|선택적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> 생성된 코드의 대상 폴더\(일반적으로 중간 폴더\)를 지정합니다.|  
|`OutputFile`|선택적 <xref:Microsoft.Build.Framework.ITaskItem> 출력 매개 변수입니다.<br /><br /> 생성된 파일의 경로를 지정합니다.  파일 이름을 사용하여 이 매개 변수를 설정하면 대상 폴더가 파일 이름에 추가됩니다.  루트를 사용하여 설정하는 경우 대상 폴더는 무시됩니다.<br /><br /> 이 매개 변수를 설정하지 않는 경우 출력 파일 이름은 대상 폴더, 임의의 파일 이름 및 지정한 언어의 기본 파일 확장명입니다.|  
  
## 설명  
 이 표에 나열된 매개 변수를 갖는 것 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)