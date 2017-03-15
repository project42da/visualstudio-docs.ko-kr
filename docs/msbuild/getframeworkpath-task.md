---
title: "GetFrameworkPath Task | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#GetFrameworkPath"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "GetFrameworkPath task [MSBuild]"
  - "MSBuild, GetFrameworkPath task"
ms.assetid: 5b7bcdd7-d4a0-442d-af29-8aadb3b10598
caps.latest.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# GetFrameworkPath Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 어셈블리에 대한 경로를 검색합니다.  
  
## 작업 매개 변수  
 다음 표에서는 `GetFrameworkPath` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`FrameworkVersion11Path`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 프레임워크 버전 1.1 어셈블리\(있는 경우\)에 대한 경로를 포함합니다.  그렇지 않으면 `null`을 반환합니다.|  
|`FrameworkVersion20Path`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 프레임워크 버전 2.0 어셈블리\(있는 경우\)에 대한 경로를 포함합니다.  그렇지 않으면 `null`을 반환합니다.|  
|`FrameworkVersion30Path`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 프레임워크 버전 3.0 어셈블리\(있는 경우\)에 대한 경로를 포함합니다.  그렇지 않으면 `null`을 반환합니다.|  
|`FrameworkVersion35Path`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 프레임워크 버전 3.5 어셈블리\(있는 경우\)에 대한 경로를 포함합니다.  그렇지 않으면 `null`을 반환합니다.|  
|`FrameworkVersion40Path`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 프레임워크 버전 4.0 어셈블리\(있는 경우\)에 대한 경로를 포함합니다.  그렇지 않으면 `null`을 반환합니다.|  
|`Path`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 최신 프레임워크 어셈블리\(있는 경우\)에 대한 경로를 포함합니다.  그렇지 않으면 `null`을 반환합니다.|  
  
## 설명  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 여러 버전을 설치한 경우 이 작업은 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서 실행하도록 디자인된 버전을 반환합니다.  
  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `GetFrameworkPath` 작업을 사용하여 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]에 대한 경로를 `FrameworkPath` 속성에 저장합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="GetPath">  
        <GetFrameworkPath>  
            <Output  
                TaskParameter="Path"  
                PropertyName="FrameworkPath" />  
        </GetFrameworkPath>  
    </Target>  
</Project>  
```  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)