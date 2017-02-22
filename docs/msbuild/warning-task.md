---
title: "Warning Task | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#Warning"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Warning task [MSBuild]"
  - "MSBuild, Warning task"
ms.assetid: 96ba5507-8b43-4f54-a1d7-9b15644dd56c
caps.latest.revision: 18
caps.handback.revision: 18
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# Warning Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

빌드하는 동안 확인된 조건문에 따라 경고를 기록합니다.  
  
## 매개 변수  
 다음 표에서는 `Warning` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`Code`|선택적 `String` 매개 변수입니다.<br /><br /> 경고에 연결할 경고 코드입니다.|  
|`File`|선택적 `String` 매개 변수입니다.<br /><br /> 관련 파일\(있는 경우\)을 지정합니다.  아무 파일도 제공하지 않으면 경고 작업이 들어 있는 파일이 사용됩니다.|  
|`HelpKeyword`|선택적 `String` 매개 변수입니다.<br /><br /> 경고와 연결할 도움말 키워드입니다.|  
|`Text`|선택적 `String` 매개 변수입니다.<br /><br /> `Condition` 매개 변수가 `true`로 확인되는 경우 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서 기록하는 경고 텍스트입니다.|  
  
## 설명  
 `Warning` 작업을 사용하면 다음 빌드 단계를 진행하기 전에 필요한 구성이나 속성이 있는지 여부를 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트에서 검사할 수 있습니다.  
  
 `Warning` 작업의 `Condition` 매개 변수가 `true`로 확인되면 `Text` 매개 변수의 값이 기록되고 빌드 프로세스가 계속 실행됩니다.  `Condition` 매개 변수가 없으면 경고 텍스트가 기록됩니다.  기록에 대한 자세한 내용은 [빌드 로그 가져오기](../msbuild/obtaining-build-logs-with-msbuild.md)을 참조하십시오.  
  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 코드 예제에서는 명령줄에 설정된 속성을 검사합니다.  속성이 설정되어 있지 않으면 프로젝트에서 경고 이벤트가 발생하고 `Warning` 작업의 `Text` 매개 변수 값이 기록됩니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="ValidateCommandLine">  
        <Warning  
            Text=" The 0 property was not set on the command line."  
            Condition="'$(0)' == ''" />  
        <Warning  
            Text=" The FREEBUILD property was not set on the command line."  
            Condition="'$(FREEBUILD)' == ''" />  
    </Target>  
    ...  
</Project>  
```  
  
## 참고 항목  
 [빌드 로그 가져오기](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [Project File Schema Reference](../msbuild/msbuild-project-file-schema-reference.md)