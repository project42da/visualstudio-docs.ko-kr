---
title: "방법: 빌드할 파일 선택 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Include 특성[MSBuild]"
  - "MSBuild, 포함하는 파일"
  - "MSBuild, 와일드카드"
ms.assetid: f5ff182f-7b3a-46fb-9335-37df54cfb8eb
caps.latest.revision: 14
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 14
---
# 방법: 빌드할 파일 선택
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

여러 개의 파일이 포함된 프로젝트를 빌드하는 경우 각 파일을 하나씩 프로젝트 파일에 나열할 수도 있고, 와일드카드를 사용하여 모든 파일을 한 디렉터리 또는 중첩 디렉터리 집합에 포함할 수도 있습니다.  
  
## 입력 지정  
 항목은 빌드에 대한 입력을 나타냅니다.  항목에 대한 자세한 내용은 [항목](../msbuild/msbuild-items.md)을 참조하십시오.  
  
 파일을 빌드에 포함하려면 해당 파일이 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트 파일의 항목 목록에 포함되어 있어야 합니다.  여러 파일을 항목 목록에 추가하기 위해 파일을 개별적으로 포함할 수도 있고 와일드카드를 사용하여 많은 파일을 한 번에 포함할 수도 있습니다.  
  
#### 항목을 개별적으로 선언하려면  
  
-   다음과 같이 `Include` 특성을 사용합니다.  
  
     `<CSFile Include="form1.cs"/>`  
  
     – 또는 –  
  
     `<VBFile Include="form1.vb"/>`  
  
    > [!NOTE]
    >  항목컬렉션의 항목이프로젝트파일과 동일한 디렉터리에 없는 경우 전체 또는항목상대 경로지정 해야 합니다.   예를 들면 `Include="..\..\form2.cs"` 형식으로 코드를 작성해야 합니다.  
  
#### 여러 항목을 선언하려면  
  
-   다음과 같이 `Include` 특성을 사용합니다.  
  
     `<CSFile Include="form1.cs;form2.cs"/>`  
  
     – 또는 –  
  
     `<VBFile Include="form1.vb;form2.vb"/>`  
  
## 와일드카드로 입력 지정  
 빌드의 입력으로 와일드카드를 사용하여 모든 파일을 재귀적으로 포함하거나 하위 디렉터리의 특정 파일만 포함할 수 있습니다.  와일드카드에 대한 자세한 내용은 [항목](../msbuild/msbuild-items.md)을 참조하십시오.  
  
 다음 예제는 다음 디렉터리와 하위 디렉터리에 그래픽 파일을 포함하는 프로젝트를 기반으로 합니다. 여기서 프로젝트 파일은 Project 디렉터리에 있습니다.  
  
 Project\\Images\\BestJpgs  
  
 Project\\Images\\ImgJpgs  
  
 Project\\Images\\ImgJpgs\\Img1  
  
#### 모든 .jpg 파일을 Images 디렉터리와 하위 디렉터리에 포함하려면  
  
-   다음과 같이 `Include` 특성을 사용합니다.  
  
     `Include="Images\**\*.jpg"`  
  
#### "img"로 시작하는 모든 .jpg 파일을 포함하려면  
  
-   다음과 같이 `Include` 특성을 사용합니다.  
  
     `Include="Images\**\img*.jpg"`  
  
#### 이름이 "jpgs"로 끝나는 디렉터리의 모든 파일을 포함하려면  
  
-   다음 `Include` 특성 중 하나를 사용합니다.  
  
     `Include="Images\**\*jpgs\*.*"`  
  
     – 또는 –  
  
     `Include="Images\**\*jpgs\*"`  
  
## 작업에 항목 전달  
 프로젝트 파일에서 작업에 @\(\) 표기법을 사용하여 전체 항목 목록을 빌드의 입력으로 지정할 수 있습니다.  모든 파일을 하나씩 나열하든지 와일드카드를 사용하든지 관계없이 이 표기법을 사용할 수 있습니다.  
  
#### 모든 Visual C\# 또는 Visual Basic 파일을 입력으로 사용하려면  
  
-   다음과 같이 `Include` 특성을 사용합니다.  
  
     `<CSC Sources="@(CSFile)">...</CSC>`  
  
     – 또는 –  
  
     `<VBC Sources="@(VBFile)">...</VBC>`  
  
> [!NOTE]
>  [Csc](../msbuild/csc-task.md) 또는 [Vbc](../msbuild/vbc-task.md) 같은 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 작업에는 `Sources` 특성을 사용하여 입력을 지정할 수 없으므로 항목에 와일드카드를 사용하여 빌드의 입력을 지정해야 합니다.  다음 예제는 프로젝트 파일에서 유효하지 않습니다.  
>   
>  `<CSC Sources="*.cs">...</CSC>`  
  
## 예제  
 다음 코드 예제에서는 모든 입력 파일을 하나씩 포함하는 프로젝트를 보여 줍니다.  
  
```  
<Project DefaultTargets="Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
    <PropertyGroup>  
        <Builtdir>built</Builtdir>  
    </PropertyGroup>  
  
    <ItemGroup>  
        <CSFile Include="Form1.cs"/>  
        <CSFile Include="AssemblyInfo.cs"/>  
  
        <Reference Include="System.dll"/>  
        <Reference Include="System.Data.dll"/>  
        <Reference Include="System.Drawing.dll"/>  
        <Reference Include="System.Windows.Forms.dll"/>  
        <Reference Include="System.XML.dll"/>  
    </ItemGroup>  
  
    <Target Name="PreBuild">  
        <Exec Command="if not exist $(builtdir) md $(builtdir)"/>  
    </Target>  
  
    <Target Name="Compile" DependsOnTargets="PreBuild">  
        <Csc Sources="@(CSFile)"  
            References="@(Reference)"  
            OutputAssembly="$(builtdir)\$(MSBuildProjectName).exe"  
            TargetType="exe" />  
    </Target>  
</Project>  
```  
  
## 예제  
 다음 코드 예제에서는 와일드카드를 사용하여 모든 .cs 파일을 포함합니다.  
  
```  
<Project DefaultTargets="Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <PropertyGroup>  
        <builtdir>built</builtdir>  
    </PropertyGroup>  
  
    <ItemGroup>  
        <CSFile Include="*.cs"/>  
  
        <Reference Include="System.dll"/>  
        <Reference Include="System.Data.dll"/>  
        <Reference Include="System.Drawing.dll"/>  
        <Reference Include="System.Windows.Forms.dll"/>  
        <Reference Include="System.XML.dll"/>  
    </ItemGroup>  
  
    <Target Name="PreBuild">  
        <Exec Command="if not exist $(builtdir) md $(builtdir)"/>  
    </Target>  
  
    <Target Name="Compile" DependsOnTargets="PreBuild">  
        <Csc Sources="@(CSFile)"  
            References="@(Reference)"  
            OutputAssembly="$(builtdir)\$(MSBuildProjectName).exe"  
            TargetType="exe" />  
    </Target>  
</Project>  
```  
  
## 참고 항목  
 [방법: 빌드에서 파일 제외](../msbuild/how-to-exclude-files-from-the-build.md)   
 [항목](../msbuild/msbuild-items.md)