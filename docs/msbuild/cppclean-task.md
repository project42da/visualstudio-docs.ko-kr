---
title: "CPPClean Task | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.task.cppclean"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
  - "C++"
helpviewer_keywords: 
  - "MSBuild (Visual C++), CPPClean task"
  - "CPPClean task (MSBuild (Visual C++))"
ms.assetid: b62a482e-8fb5-4999-b50b-6605a078e291
caps.latest.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 5
---
# CPPClean Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual C\+\+ 프로젝트를 빌드할 때 MSBuild가 만드는 임시 파일을 삭제합니다.  빌드 파일 삭제 프로세스를 *정리*라고 합니다.  
  
## 매개 변수  
 다음 표에서는 **CPPClean**  작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|**DeletedFiles**|선택적 `ITaskItem[]` 출력 매개 변수입니다.<br /><br /> 작업에서 사용하고 내보낼 수 있는 MSBuild 출력 파일 항목의 배열을 정의합니다.|  
|**DoDelete**|선택적 **Boolean** 매개 변수입니다.<br /><br /> `true`인 경우 임시 빌드 파일을 정리합니다.|  
|**FilePatternsToDeleteOnClean**|필수적 `String` 매개 변수입니다.<br /><br /> 정리할 파일의 파일 확장명의 세미콜론으로 구분된 목록을 지정합니다.|  
|**FilesExcludedFromClean**|선택적 `String` 매개 변수입니다.<br /><br /> 정리하지 않을 파일의 세미콜론으로 구분된 목록을 지정합니다.|  
|**FoldersToClean**|필수적 `String` 매개 변수입니다.<br /><br /> 정리할 디렉터리의 세미콜론으로 구분된 목록을 지정합니다.  전체 또는 상대 경로를 지정할 수 있으며 경로는 와일드카드 기호\(**\***\)를 포함할 수 있습니다.|  
  
## 설명  
  
## 참고 항목  
 [Task Reference](../msbuild/msbuild-task-reference.md)