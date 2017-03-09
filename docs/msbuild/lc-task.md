---
title: "LC Task | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#LC"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MSBuild, LC task"
  - "LC task [MSBuild]"
ms.assetid: d5a53472-6f2a-42b8-a6db-593ca99c9790
caps.latest.revision: 15
caps.handback.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# LC Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

.licx 파일에서 .license 파일을 생성하는 LC.exe를 래핑합니다.  LC.exe에 대한 자세한 내용은 [Lc.exe\(라이선스 컴파일러\)](../Topic/Lc.exe%20\(License%20Compiler\).md)를 참조하십시오.  
  
## 매개 변수  
 다음 표에서는 `LC` 작업의 매개 변수를 보여 줍니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`LicenseTarget`|필수적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> .licenses 파일이 생성되는 대상 실행 파일을 지정합니다.|  
|`NoLogo`|선택적 `Boolean` 매개 변수입니다.<br /><br /> Microsoft 시작 배너를 표시하지 않습니다.|  
|`OutputDirectory`|선택적 `String` 매개 변수입니다.<br /><br /> 출력된 .licenses 파일을 배치할 디렉터리를 지정합니다.|  
|`OutputLicense`|선택적 <xref:Microsoft.Build.Framework.ITaskItem> 출력 매개 변수입니다.<br /><br /> .licenses 파일의 이름을 지정합니다.  이름을 지정하지 않으면 .licx 파일의 이름이 사용되고 .licenses 파일이 .licx 파일과 동일한 디렉터리에 배치됩니다.|  
|`ReferencedAssemblies`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> .license 파일을 생성할 때 로드할 참조된 구성 요소를 지정합니다.|  
|`SdkToolsPath`|선택적 `String` 매개 변수입니다.<br /><br /> resgen.exe와 같이 SDK 도구에 대한 경로를 지정합니다.|  
|`Sources`|필수적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> .licenses 파일에 포함할 라이센스가 있는 구성 요소가 들어 있는 항목을 지정합니다.  자세한 내용은 [Lc.exe\(라이선스 컴파일러\)](../Topic/Lc.exe%20\(License%20Compiler\).md)에서 `/complist` 스위치에 대한 설명을 참조하십시오.|  
  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.ToolTask> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.ToolTaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [ToolTaskExtension Base Class](../msbuild/tooltaskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `LC` 작업을 사용하여 라이센스를 컴파일합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
<!-- Item declarations, etc -->  
  
    <Target Name="CompileLicenses">  
        <LC  
            Sources="@(LicxFile)"  
            LicenseTarget="$(TargetFileName)"  
            OutputDirectory="$(IntermediateOutputPath)"  
            OutputLicenses="$(IntermediateOutputPath)$(TargetFileName).licenses"  
            ReferencedAssemblies="@(ReferencePath);@(ReferenceDependencyPaths)">  
  
            <Output  
                TaskParameter="OutputLicenses"  
                ItemName="CompiledLicenseFile"/>  
        </LC>  
    </Target>  
</Project>  
```  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)