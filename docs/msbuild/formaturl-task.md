---
title: "FormatUrl Task | Microsoft Docs"
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
  - "MSBuild, FormatUrl task"
  - "FormatUrl task [MSBuild]"
ms.assetid: 81114b67-520f-43b5-8891-224f68a78516
caps.latest.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 5
---
# FormatUrl Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

URL을 정확한 URL 형식으로 변환합니다.  
  
## 매개 변수  
 다음 표에서는 `FormatUrl` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`InputUrl`|선택적 `String` 매개 변수입니다.<br /><br /> 서식을 지정할 URL을 지정합니다.|  
|`OutputUrl`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 서식 있는 URL을 지정합니다.|  
  
## 설명  
 표에 나열된 매개 변수를 갖는 것 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)