---
title: "방법: 빌드 정리 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디렉터리[.NET Framework], 출력 항목용"
  - "Exec 작업[MSBuild]"
  - "MSBuild, 빌드 정리"
  - "출력, 항목 제거"
ms.assetid: 999ba473-b0c4-45c7-930a-63ea7a510509
caps.latest.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 13
---
# 방법: 빌드 정리
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

빌드를 정리할 경우 프로젝트와 구성 요소 파일만 남고 모든 중간 파일과 출력 파일이 삭제됩니다.  프로젝트와 구성 요소 파일을 사용하여 중간 파일과 출력 파일의 새 인스턴스를 빌드할 수 있습니다.  [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]와 함께 제공되는 일반 작업 라이브러리에는 시스템 명령을 실행하는 데 사용할 수 있는 [Exec](../msbuild/exec-task.md) 작업이 포함되어 있습니다.  작업 라이브러리에 대한 자세한 내용은 [Task Reference](../msbuild/msbuild-task-reference.md)를 참조하십시오.  
  
## 출력 항목을 위한 디렉터리 만들기  
 기본적으로 프로젝트를 컴파일할 때 만들어지는 .exe 파일은 프로젝트 및 소스 파일과 동일한 디렉터리에 배치됩니다.  그러나 일반적으로 출력 항목은 별도의 디렉터리에 만들어집니다.  
  
#### 출력 항목을 위한 디렉터리를 만들려면  
  
1.  `Property` 요소를 사용하여 디렉터리의 위치와 이름을 정의합니다.  예를 들어, 프로젝트와 소스 파일이 들어 있는 디렉터리에 `BuiltApp`라는 디렉터리를 만듭니다.  
  
     `<builtdir>BuiltApp</builtdir>`  
  
2.  해당 디렉터리가 없으면 [MakeDir](../msbuild/makedir-task.md) 작업을 사용하여 디렉터리를 만듭니다.  예를 들면 다음과 같습니다.  
  
     `<MakeDir Directories = "$(builtdir)"`  
  
     `Condition = "!Exists('$(builtdir)')" />`  
  
## 출력 항목 제거  
 중간 파일과 출력 파일의 새 인스턴스를 만들기 전에, 중간 파일과 출력 파일의 이전 인스턴스를 모두 지우고자 할 수 있습니다.  [RemoveDir](../msbuild/removedir-task.md) 작업을 사용하여 디렉터리 및 디렉터리에 포함된 모든 파일과 디렉터리를 디스크에서 삭제합니다.  
  
#### 디렉터리 및 디렉터리에 포함된 모든 파일을 제거하려면  
  
-   `RemoveDir` 작업을 사용하여 디렉터리를 제거합니다.  예를 들면 다음과 같습니다.  
  
     `<RemoveDir Directories="$(builtdir)" />`  
  
## 예제  
 다음의 코드 예제 프로젝트에는 `RemoveDir` 작업을 사용하여 디렉터리 및 디렉터리가 포함된 모든 파일과 디렉터리를 삭제하는 `Clean`이라는 새 대상이 포함되어 있습니다.  또한 이 예제에서 `Compile` 대상은 빌드가 정리될 때 삭제되는 출력 항목을 위한 별도의 디렉터리를 만듭니다.  
  
 `Compile`이 기본 대상으로 정의되므로 다른 대상을 지정하지 않으면 이 대상이 자동으로 사용됩니다.  다른 대상을 지정하려면 명령줄 스위치 **\/target**을 사용합니다.  예를 들면 다음과 같습니다.  
  
 `msbuild <file name>.proj /target:Clean`  
  
 **\/target** 스위치는 간단하게 **\/t**로 사용될 수 있으며 대상을 두 개 이상 지정할 수 있습니다.  예를 들어, `Clean` 대상과 `Compile` 대상을 차례로 사용하려면 다음과 같이 입력합니다.  
  
 `msbuild <file name>.proj /t:Clean;Compile`  
  
```  
<Project DefaultTargets = "Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <PropertyGroup>  
        <!-- Set the application name as a property -->  
        <name>HelloWorldCS</name>  
  
        <!-- Set the output folder as a property -->  
        <builtdir>BuiltApp</builtdir>  
    </PropertyGroup>  
  
    <ItemGroup>  
        <!-- Specify the inputs by type and file name -->  
        <CSFile Include = "consolehwcs1.cs"/>  
    </ItemGroup>  
  
    <Target Name = "Compile">  
        <!-- Check whether an output folder exists and create  
        one if necessary -->  
        <MakeDir Directories = "$(builtdir)"   
            Condition = "!Exists('$(builtdir)')" />  
  
        <!-- Run the Visual C# compiler -->  
        <CSC Sources = "@(CSFile)"   
            OutputAssembly = "$(BuiltDir)\$(appname).exe">  
            <Output TaskParameter = "OutputAssembly"  
                ItemName = "EXEFile" />  
        </CSC>  
  
        <!-- Log the file name of the output file -->  
        <Message Text="The output file is @(EXEFile)"/>  
    </Target>  
  
    <Target Name = "Clean">  
        <RemoveDir Directories="$(builtdir)" />  
    </Target>  
</Project>  
```  
  
## 참고 항목  
 [Exec Task](../msbuild/exec-task.md)   
 [MakeDir Task](../msbuild/makedir-task.md)   
 [RemoveDir Task](../msbuild/removedir-task.md)   
 [Csc Task](../msbuild/csc-task.md)   
 [대상](../msbuild/msbuild-targets.md)