---
title: "GetFrameworkSdkPath Task | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#GetFrameworkSdkPath"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "GetFrameworkSdkPath task [MSBuild]"
  - "MSBuild, GetFrameworkSdkPath task"
ms.assetid: 2ef82b98-02b6-40cf-a9b5-f0e882fb5064
caps.latest.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 10
---
# GetFrameworkSdkPath Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]에 대한 경로를 검색합니다.  
  
## 작업 매개 변수  
 다음 표에서는 `GetFrameworkSdkPath` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`FrameworkSdkVersion20Path`|선택적 `String` 읽기 전용 출력 매개 변수입니다.<br /><br /> .NET SDK 버전 2.0\(있는 경우\)에 대한 경로를 반환합니다.  그렇지 않으면 `String.Empty`을 반환합니다.|  
|`FrameworkSdkVersion35Path`|선택적 `String` 읽기 전용 출력 매개 변수입니다.<br /><br /> .NET SDK 버전 3.5\(있는 경우\)에 대한 경로를 반환합니다.  그렇지 않으면 `String.Empty`을 반환합니다.|  
|`FrameworkSdkVersion40Path`|선택적 `String` 읽기 전용 출력 매개 변수입니다.<br /><br /> .NET SDK 버전 4.0\(있는 경우\)에 대한 경로를 반환합니다.  그렇지 않으면 `String.Empty`을 반환합니다.|  
|`Path`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 최신 .NET SDK\(버전에 관계 없이 있는 경우\)에 대한 경로를 포함합니다.  그렇지 않으면 `String.Empty`을 반환합니다.|  
  
## 설명  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `GetFrameworkSdkPath` 작업을 사용하여 [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)]에 대한 경로를 `SdkPath` 속성에 저장합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="GetPath">  
        <GetFrameworkSdkPath>  
            <Output  
                TaskParameter="Path"  
                PropertyName="SdkPath" />  
        </GetFrameworkSdkPath>  
        <Message Text="$(SdkPath)"/>  
    </Target>  
</Project>  
```  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)