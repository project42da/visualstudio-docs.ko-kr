---
title: "방법: Visual Studio 빌드 프로세스 확장 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSBuild, DependsOn 속성"
  - "MSBuild, Visual Studio 빌드 확장"
  - "MSBuild, DependsOn 속성 재정의"
  - "MSBuild, 미리 정의된 대상 재정의"
ms.assetid: cb077613-4a59-41b7-96ec-d8516689163c
caps.latest.revision: 8
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 8
---
# 방법: Visual Studio 빌드 프로세스 확장
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 빌드 프로세스는 프로젝트 파일로 가져온 일련의 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] .targets 파일로 정의됩니다.  가져온 이러한 파일 중 하나인 Microsoft.Common.targets를 확장하면 빌드 프로세스의 일부 지점에서 사용자 지정 작업을 실행할 수 있습니다.  이 항목에서는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 빌드 프로세스를 확장하는 데 사용할 수 있는 두 가지 방법을 설명합니다.  
  
-   Microsoft.Common.targets에 미리 정의된 특정 대상 재정의  
  
-   Microsoft.Common.targets에 정의된 "DependsOn" 속성 재정의  
  
## 미리 정의된 대상 재정의  
 Microsoft.Common.targets 파일에는 빌드 프로세스에서 일부 주요 대상의 전후에 호출되는 일련의 미리 정의된 빈 대상이 들어 있습니다.  예를 들어 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]는 주 `CoreBuild` 대상을 호출하기 전에 `BeforeBuild` 대상을 호출하고 `CoreBuild` 대상을 호출한 후에는 `AfterBuild` 대상을 호출합니다.  기본적으로 Microsoft.Common.targets의 빈 대상은 아무 작업도 수행하지 않지만 Microsoft.Common.targets를 가져오는 프로젝트 파일에서 원하는 대상을 정의하여 빈 대상의 기본 동작을 재정의할 수 있습니다.  이렇게 하면 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 작업을 사용하여 빌드 프로세스를 보다 강력하게 제어할 수 있습니다.  
  
#### 미리 정의된 대상을 재정의하려면  
  
1.  Microsoft.Common.targets에서 재정의하려는 미리 정의된 대상을 식별합니다.  안전하게 재정의할 수 있는 대상의 전체 목록은 아래 표를 참조하십시오.  
  
2.  프로젝트 파일의 끝에서 `</Project>` 태그의 바로 앞에 대상을 정의합니다.  예를 들면 다음과 같습니다.  
  
    ```  
    <Project>  
        ...  
        <Target Name="BeforeBuild">  
            <!-- Insert tasks to run before build here -->  
        </Target>  
        <Target Name="AfterBuild">  
            <!-- Insert tasks to run after build here -->  
        </Target>  
    </Project>  
    ```  
  
3.  프로젝트 파일을 빌드합니다.  
  
 다음 표에서는 안전하게 재정의할 수 있는 Microsoft.Common.targets의 모든 대상을 보여 줍니다.  
  
|대상 이름|설명|  
|-----------|--------|  
|`BeforeCompile`, `AfterCompile`|이러한 대상 중 하나에 삽입된 작업은 핵심 컴파일이 수행되기 전후에 실행됩니다.  사용자 지정은 대부분 이러한 두 대상 중 하나에서 수행합니다.|  
|`BeforeBuild`, `AfterBuild`|이러한 대상 중 하나에 삽입된 작업은 빌드의 다른 모든 작업이 수행되기 전후에 실행됩니다. **Note:**  `BeforeBuild` 및 `AfterBuild` 대상은 대부분의 프로젝트 파일 끝에 있는 주석에 이미 정의되어 있습니다.  따라서 프로젝트 파일에 빌드 전 이벤트와 빌드 후 이벤트를 쉽게 추가할 수 있습니다.|  
|`BeforeRebuild`, `AfterRebuild`|이러한 대상 중 하나에 삽입된 작업은 핵심 재빌드 기능이 호출되기 전후에 실행됩니다.  Microsoft.Common.targets에서 대상이 실행되는 순서는 `BeforeRebuild`, `Clean`, `Build` 및 `AfterRebuild`입니다.|  
|`BeforeClean`, `AfterClean`|이러한 대상 중 하나에 삽입된 작업은 핵심 정리 기능이 호출되기 전후에 실행됩니다.|  
|`BeforePublish`, `AfterPublish`|이러한 대상 중 하나에 삽입된 작업은 핵심 게시 기능이 호출되기 전후에 실행됩니다.|  
|`BeforeResolveReference`, `AfterResolveReferences`|이러한 대상 중 하나에 삽입된 작업은 어셈블리 참조가 확인되기 전후에 실행됩니다.|  
|`BeforeResGen`, `AfterResGen`|이러한 대상 중 하나에 삽입된 작업은 리소스가 생성되기 전후에 실행됩니다.|  
  
## "DependsOn" 속성 재정의  
 미리 정의된 대상을 재정의하면 빌드 프로세스를 쉽게 확장할 수 있지만 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 대상의 정의가 순차적으로 평가되므로 사용자가 이미 재정의한 대상을 해당 프로젝트를 가져간 다른 프로젝트에서 재정의하지 못하게 할 수 없습니다.  예를 들어, 다른 프로젝트를 모두 가져온 후에 프로젝트 파일에 정의된 마지막 `AfterBuild` 대상이 빌드 과정에서 사용됩니다.  
  
 Microsoft.Common.targets 파일 전체에서 `DependsOnTargets` 특성에 사용되는 "DependsOn" 속성을 재정의하면 대상이 임의로 재정의되는 것을 방지할 수 있습니다.  예를 들어, `Build` 대상의 `DependsOnTargets` 특성 값이 `"$(BuildDependsOn)"`인 다음과 같은 경우를  가정할 수 있습니다.  
  
```  
<Target Name="Build" DependsOnTargets="$(BuildDependsOn)"/>  
```  
  
 이 XML은 `Build` 대상을 실행하기 전에 먼저 `BuildDependsOn` 속성에 지정된 대상을 모두 실행해야 함을 나타냅니다.  `BuildDependsOn` 속성은 다음과 같이 정의됩니다.  
  
```  
<PropertyGroup>  
    <BuildDependsOn>  
        BeforeBuild;  
        CoreBuild;  
        AfterBuild  
    </BuildDependsOn>  
</PropertyGroup>  
```  
  
 프로젝트 파일의 끝에서 `BuildDependsOn`이라는 다른 속성을 선언하여 이 속성 값을 재정의할 수 있습니다.  새 속성에 이전 `BuildDependsOn` 속성을 포함하면 대상 목록의 시작과 끝 부분에 새 대상을 추가할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
<PropertyGroup>  
    <BuildDependsOn>  
        MyCustomTarget1;  
        $(BuildDependsOn);  
        MyCustomTarget2  
    </BuildDependsOn>  
</PropertyGroup>  
  
<Target Name="MyCustomTarget1">  
    <Message Text="Running MyCustomTarget1..."/>  
</Target>  
<Target Name="MyCustomTarget2">  
    <Message Text="Running MyCustomTarget2..."/>  
</Target>  
```  
  
 해당 프로젝트 파일을 가져간 다른 프로젝트에서는 사용자가 사용자 지정한 내용을 재정의하지 않고도 이러한 속성을 재정의할 수 있습니다.  
  
#### "DependsOn" 속성을 재정의하려면  
  
1.  Microsoft.Common.targets에서 재정의하려는 미리 정의된 "DependsOn" 속성을 식별합니다.  일반적으로 재정의되는 "DependsOn" 속성 목록은 아래 표를 참조하십시오.  
  
2.  프로젝트 파일의 끝에서 속성의 다른 인스턴스를 정의합니다.  `$(BuildDependsOn)`과 같이 새 속성에 원래 속성을 포함합니다.  
  
3.  속성 정의의 앞이나 뒤에 사용자 지정 대상을 정의합니다.  
  
4.  프로젝트 파일을 빌드합니다.  
  
### 일반적으로 재정의되는 "DependsOn" 속성  
  
|속성 이름|설명|  
|-----------|--------|  
|`BuildDependsOn`|전체 빌드 프로세스 전후에 사용자 지정 대상을 삽입하려는 경우 재정의할 속성입니다.|  
|`CleanDependsOn`|사용자 지정 빌드 프로세스의 출력을 정리하려는 경우 재정의할 속성입니다.|  
|`CompileDependsOn`|컴파일 단계 전후에 사용자 지정 프로세스를 삽입하려는 경우 재정의할 속성입니다.|  
  
## 참고 항목  
 [Visual Studio 통합](../msbuild/visual-studio-integration-msbuild.md)   
 [MSBuild 개념](../msbuild/msbuild-concepts.md)   
 [.Targets Files](../msbuild/msbuild-dot-targets-files.md)