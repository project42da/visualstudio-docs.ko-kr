---
title: "MSBuild Conditional Constructs | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<Choose> Element [MSBuild]"
  - "Choose Element [MSBuild]"
  - "conditional constructs [MSBuild]"
  - "MSBuild, conditional constructs"
  - "<When> Element [MSBuild]"
  - "<Otherwise> Element [MSBuild]"
  - "Otherwise Element [MSBuild]"
  - "When Element [MSBuild]"
ms.assetid: dd54258e-f4fb-448f-9da4-d1817e0cbaf2
caps.latest.revision: 9
caps.handback.revision: 9
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# MSBuild Conditional Constructs
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 [Choose](../msbuild/choose-element-msbuild.md), [When](../msbuild/when-element-msbuild.md) 및 [Otherwise](../msbuild/otherwise-element-msbuild.md) 요소의 양자 택일\(either\/or\) 처리를 위한 메커니즘을 제공합니다.  
  
## Choose 요소 사용  
 `Choose` 요소에는 `true`로 확인될 때까지 위에서 아래 순서대로 테스트되는 `Condition` 특성을 갖는 일련의 `When` 요소가 포함됩니다.  둘 이상의 `When` 요소가 `true`인 경우 첫째 요소만 사용됩니다.  `When` 요소에 `true`인 조건이 없으면 `Otherwise` 요소가 있는 경우 이 요소가 실행됩니다.  
  
 `Choose` 요소는 `Project`, `When` 및 `Otherwise` 요소의 자식 요소로 사용될 수 있습니다.  `When` 및 `Otherwise` 요소는 `ItemGroup`, `PropertyGroup` 또는 `Choose` 자식 요소를 가질 수 있습니다.  
  
## 예제  
 다음 예제에서는 양자 택일\(either\/or\) 처리를 위해 `Choose` 및 `When` 요소를 사용합니다.  프로젝트의 속성과 항목은 `Configuration` 속성의 값에 따라 설정됩니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
    <PropertyGroup>  
        <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
        <OutputType>Exe</OutputType>  
        <RootNamespace>ConsoleApplication1</RootNamespace>  
        <AssemblyName>ConsoleApplication1</AssemblyName>  
        <WarningLevel>4</WarningLevel>  
    </PropertyGroup>  
    <Choose>  
        <When Condition=" '$(Configuration)'=='Debug' ">  
            <PropertyGroup>  
                <DebugSymbols>true</DebugSymbols>  
                <DebugType>full</DebugType>  
                <Optimize>false</Optimize>  
                <OutputPath>.\bin\Debug\</OutputPath>  
                <DefineConstants>DEBUG;TRACE</DefineConstants>  
            </PropertyGroup>  
            <ItemGroup>  
                <Compile Include="UnitTesting\*.cs" />  
                <Reference Include="NUnit.dll" />  
            </ItemGroup>  
        </When>  
        <When Condition=" '$(Configuration)'=='retail' ">  
            <PropertyGroup>  
                <DebugSymbols>false</DebugSymbols>  
                <Optimize>true</Optimize>  
                <OutputPath>.\bin\Release\</OutputPath>  
                <DefineConstants>TRACE</DefineConstants>  
            </PropertyGroup>  
        </When>  
    </Choose>  
    <!-- Rest of Project -->  
</Project>  
```  
  
## 참고 항목  
 [Choose Element \(MSBuild\)](../msbuild/choose-element-msbuild.md)   
 [When Element \(MSBuild\)](../msbuild/when-element-msbuild.md)   
 [Otherwise Element \(MSBuild\)](../msbuild/otherwise-element-msbuild.md)   
 [MSBuild Reference](../msbuild/msbuild-reference.md)