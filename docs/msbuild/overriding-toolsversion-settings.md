---
title: "ToolsVersion 설정 재정의 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSBuild, 솔루션 빌드"
  - "MSBuild, ToolsVersion 설정 재정의"
ms.assetid: ccd42c07-0fb6-4e8b-9ebb-a6a6db18aa2e
caps.latest.revision: 24
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 24
---
# ToolsVersion 설정 재정의
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다음 세 가지 방법 중 하나로 프로젝트 및 솔루션에 대한 도구 집합을 변경할 수 있습니다.  
  
1.  명령줄에서 프로젝트 또는 솔루션을 빌드할 때 `/ToolsVersion` 스위치\(또는 간단히 `/tv`\)를 사용  
  
2.  MSBuild 작업에서 `ToolsVersion` 매개 변수 설정  
  
3.  솔루션 내에서 특정 프로젝트에 대한 `$(ProjectToolsVersion)` 속성을 설정합니다.  이렇게 하면 다른 프로젝트와 다른 도구 집합 버전을 사용하여 솔루션에서 프로젝트를 빌드할 수 있습니다.  
  
## 명령줄 빌드에서 프로젝트 및 솔루션의 ToolsVersion 설정 재정의  
 일반적으로 Visual Studio 프로젝트는 프로젝트 파일에 지정된 ToolsVersion을 사용하여 빌드되지만 명령줄에서 `/ToolsVersion` \(또는 `/tv`\) 스위치를 사용하여 해당 값을 재정의하면 다른 도구 집합을 사용하여 모든 프로젝트와 해당 프로젝트 간 종속성을 빌드할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
msbuild.exe someproj.proj /tv:12.0 /p:Configuration=Debug  
```  
  
 이 예제에서는 모든 프로젝트가 ToolsVersion 12.0를 사용하여 빌드됩니다. 자세한 내용은 이 항목의 뒷부분에 있는 "우선 순위" 단원을 참조하십시오.  
  
 명령줄에서 `/tv` 스위치를 사용하는 경우 선택적으로 개별 프로젝트에 `$(ProjectToolsVersion)` 속성을 사용하여 솔루션에 있는 다른 프로젝트와 다른 ToolsVersion 값을 사용하여 이러한 프로젝트를 빌드할 수 있습니다.  
  
## MSBuild 작업의 ToolsVersion 매개 변수를 사용하여 ToolsVersion 설정 재정의  
 MSBuild 작업은 한 프로젝트를 기반으로 다른 프로젝트를 빌드하는 기본 방법입니다.  MSBuild 작업에는 프로젝트에 지정된 것과 다른 ToolsVersion을 사용하여 프로젝트를 빌드할 수 있도록 `ToolsVersion`이라는 선택적 작업 매개 변수가 제공됩니다.  다음 예제에서는 이 매개 변수를 사용하는 방법을 보여줍니다.  
  
1.  이름이 `projectA.proj`이며 다음 코드를 포함한 파일을 만듭니다.  
  
    ```  
    <Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003"  
    ToolsVersion="12.0">  
  
        <Target Name="go" >   
            <Message Text="projectA.proj" />  
            <Message Text="MSBuildToolsVersion: $(MSBuildToolsVersion)" />  
            <Message Text="MSBuildToolsPath:    $(MSBuildToolsPath)" />  
  
            <MSBuild Projects="projectB.proj"  
                ToolsVersion="2.0"  
                Targets="go" />  
        </Target>  
    </Project>  
    ```  
  
2.  이름이 `projectB.proj`이며 다음 코드를 포함한 다른 파일을 만듭니다.  
  
    ```  
    <Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003"  
    ToolsVersion="12.0">  
  
        <Target Name="go">  
            <Message Text="projectB.proj" />  
            <Message Text="MSBuildToolsVersion: $(MSBuildToolsVersion)" />  
            <Message Text="MSBuildToolsPath:    $(MSBuildToolsPath)" />  
        </Target>  
    </Project>  
    ```  
  
3.  명령 프롬프트에 다음 명령을 입력합니다.  
  
    ```  
    msbuild projectA.proj /t:go /toolsversion:3.5  
    ```  
  
4.  다음 출력이 표시됩니다.  `projectA`의 경우 명령 줄의 `/toolsversion:3.5` 설정이 `Project` 태그에 있는 `ToolsVersion=12.0` 설정을 재정의합니다.  
  
     `ProjectB`작업에 의해 호출됩니다`projectA`.  해당 작업에는 `projectB`에 대한 기타 `ToolsVersion` 설정을 재정의하는 `ToolsVersion=2.0`이 있습니다.  
  
    ```  
    Output:  
      projectA.proj  
      MSBuildToolsVersion: 3.5  
      MSBuildToolsPath:    C:\Windows\Microsoft.NET\Framework\v3.5  
  
      projectB.proj  
      MSBuildToolsVersion: 2.0  
      MSBuildToolsPath:    C:\Windows\Microsoft.NET\Framework\v2.0.50727  
    ```  
  
## 우선 순위  
 `ToolsVersion`을 확인하기 위해 사용되는 최상위에서 최하위 순으로 나타내는 우선 순위 목록입니다.  
  
1.  프로젝트를 빌드하는 데 사용된 MSBuild 작업에 대한 `ToolsVersion` 특성입니다\(있는 경우\).  
  
2.  `/toolsversion`\(또는 `/tv`\)은 msbuild.exe 명령\(있는 경우\)에 사용되는 스위치입니다.  
  
3.  환경 변수 `MSBUILDTREATALLTOOLSVERSIONSASCURRENT`가 설정된 경우 현재 `ToolsVersion`을 사용합니다.  
  
4.  환경 변수 `MSBUILDTREATHIGHERTOOLSVERSIONASCURRENT`가 설정되었고 프로젝트 파일에 정의된 `ToolsVersion`가 현재 `ToolsVersion`보다 큰 경우 현재 `ToolsVersion`를 사용합니다.  
  
5.  환경 변수 `MSBUILDLEGACYDEFAULTTOOLSVERSION`가 설정되었거나 `ToolsVersion`가 설정되지 않은 경우 다음 단계를 사용합니다.  
  
    1.  프로젝트 파일의 [Project](../msbuild/project-element-msbuild.md) 요소에 대한 `ToolsVersion` 특성입니다.  이 특성이 존재하지 않는 경우 현재 버전으로 간주됩니다.  
  
    2.  MSBuild.exe.config 파일의 기본 도구 버전입니다.  
  
    3.  레지스트리의 기본 도구 버전  자세한 내용은 [표준 및 사용자 지정 도구 집합 구성](../msbuild/standard-and-custom-toolset-configurations.md)을 참조하십시오.  
  
6.  환경 변수 `MSBUILDLEGACYDEFAULTTOOLSVERSION`가 설정된 경우 다음 단계를 사용합니다.  
  
    1.  환경 변수 `MSBUILDDEFAULTTOOLSVERSION`가 존재하는 `ToolsVersion`에 설정된 경우 사용하십시오.  
  
    2.  `DefaultOverrideToolsVersion`이 MSBuild.exe.config에 설정되어 있으면 사용하십시오.  
  
    3.  `DefaultOverrideToolsVersion`이 레지스트리에 설정되어 있는 경우 이 버전을 사용합니다.  
  
    4.  그렇지 않으면 현재 `ToolsVersion`을 사용합니다.  
  
## 참고 항목  
 [멀티 타기팅](../msbuild/msbuild-multitargeting-overview.md)   
 [MSBuild 개념](../msbuild/msbuild-concepts.md)   
 [도구 집합\(ToolsVersion\)](../msbuild/msbuild-toolset-toolsversion.md)   
 [표준 및 사용자 지정 도구 집합 구성](../msbuild/standard-and-custom-toolset-configurations.md)