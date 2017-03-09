---
title: "Exec Task | Microsoft Docs"
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
  - "http://schemas.microsoft.com/developer/msbuild/2003#Exec"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Exec task [MSBuild]"
  - "MSBuild, Exec task"
ms.assetid: c9b7525a-b1c9-40fc-8bce-77a5b8f960d8
caps.latest.revision: 20
caps.handback.revision: 20
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# Exec Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지정된 인수를 사용하여 지정된 프로그램이나 명령을 실행합니다.  
  
## 매개 변수  
 다음 표에서는 `Exec` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`Command`|필수적 `String` 매개 변수입니다.<br /><br /> 실행할 명령입니다.  이 명령은 attrib와 같은 시스템 명령일 수도 있고 program.exe, runprogram.bat 또는 setup.msi와 같은 실행 파일일 수도 있습니다.<br /><br /> 이 매개 변수는 여러 줄의 명령을 포함할 수 있습니다.  여러 개의 명령을 배치 파일에 저장한 다음 이 매개 변수를 사용하여 실행할 수도 있습니다.|  
|`CustomErrorRegularExpression`|선택적 `String` 매개 변수입니다.<br /><br /> 도구 출력에서 오류 줄을 발견하는 데 사용할 정규식을 지정합니다.  이는 예외적으로 형식이 지정된 출력을 만드는 도구에 유용합니다.|  
|`CustomWarningRegularExpression`|선택적 `String` 매개 변수입니다.<br /><br /> 도구 출력에서 경고 줄을 발견하는 데 사용할 정규식을 지정합니다.  이는 예외적으로 형식이 지정된 출력을 만드는 도구에 유용합니다.|  
|`ExitCode`|선택적 `Int32` 읽기 전용 출력 매개 변수입니다.<br /><br /> 실행한 명령에서 제공하는 종료 코드를 지정합니다.|  
|`IgnoreExitCode`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 실행한 명령에서 제공하는 종료 코드를 작업에서 무시합니다.  그렇지 않으면 실행한 명령에서 0이 아닌 종료 코드를 반환하는 경우 작업에서 `false`를 반환합니다.|  
|`IgnoreStandardErrorWarningFormat`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `false`인 경우 표준 오류\/경고 형식과 일치하는 출력에서 줄을 선택하고 오류\/경고로 기록합니다.  `true`인 경우 이 동작을 사용하지 않습니다.|  
|`Outputs`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 작업의 출력 항목이 들어 있습니다.  `Exec` 작업에서는 이러한 항목이 자동으로 설정되지 않습니다.  대신 사용자가 직접 이를 제공하여 프로젝트에서 나중에 사용할 수 있습니다.|  
|`StdErrEncoding`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 캡처한 작업 표준 오류 스트림의 인코딩을 지정합니다.  기본값은 현재 콘솔 출력 인코딩입니다.|  
|`StdOutEncoding`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 캡처한 작업 표준 출력 스트림의 인코딩을 지정합니다.  기본값은 현재 콘솔 출력 인코딩입니다.|  
|`WorkingDirectory`|선택적 `String` 매개 변수입니다.<br /><br /> 명령을 실행할 디렉터리를 지정합니다.|  
  
## 설명  
 이 작업은 수행하려는 작업에 대한 특정 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 작업을 사용할 수 없는 경우에 유용합니다.  하지만 `Exec` 작업의 경우 더 구체적인 작업과 달리 실행하는 명령 또는 도구에서 출력을 수집할 수 없습니다.  
  
 `Exec` 작업은 프로세스를 직접 호출하는 대신 cmd.exe를 호출합니다.  
  
 위에 나열된 매개 변수 외에도 이 문서는 <xref:Microsoft.Build.Utilities.ToolTask> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.ToolTaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [ToolTaskExtension Base Class](../msbuild/tooltaskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `Exec` 작업을 사용하여 명령을 실행합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Binaries Include="*.dll;*.exe"/>  
    </ItemGroup>  
  
    <Target Name="SetACL">  
        <!-- set security on binaries-->  
        <Exec Command="echo y| cacls %(Binaries.Identity) /G everyone:R"/>  
    </Target>  
  
</Project>  
```  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)