---
title: "FindInList Task | Microsoft Docs"
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
  - "FindInList task [MSBuild]"
  - "MSBuild, FindInList task"
ms.assetid: d49b9f84-52a2-4242-9269-b741a7a7e9f7
caps.latest.revision: 7
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 7
---
# FindInList Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지정된 목록에서 일치하는 itemspec이 있는 항목을 찾습니다.  
  
## 매개 변수  
 다음 표에서는 [FindInList Task](../msbuild/findinlist-task.md)의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`CaseSensitive`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 검색에서 대\/소문자를 구분하고, 그렇지 않으면 대\/소문자를 구분하지 않습니다.  기본값은 `true`으로,|  
|`FindLastMatch`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 일치하는 마지막 항목이 반환되고, 그렇지 않으면 일치하는 첫 번째 항목이 반환됩니다.  기본값은 `false`으로,|  
|`ItemFound`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 읽기 전용 출력 매개 변수입니다.<br /><br /> 목록에서 처음으로 일치하는 항목\(있는 경우\)입니다.|  
|`ItemSpecToFind`|필수적 `String` 매개 변수입니다.<br /><br /> 검색할 itemspec입니다.|  
|`List`|필수적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> itemspec을 검색할 목록입니다.|  
|`MatchFileNameOnly`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 itemspec의 파일 이름 부분에서만 일치 여부를 확인하고, 그렇지 않으면 전체 itemspec의 일치 여부를 확인합니다.  기본값은 `true`으로,|  
  
## 설명  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)