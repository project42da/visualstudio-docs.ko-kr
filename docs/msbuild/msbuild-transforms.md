---
title: "MSBuild 변환 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSBuild, 변환"
  - "변환[MSBuild]"
ms.assetid: d0bcfc3c-14fa-455e-805c-63ccffa4a3bf
caps.latest.revision: 13
caps.handback.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# MSBuild 변환
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

변환은 하나의 항목 목록을 다른 항목 목록으로 일대일 변환하는 것입니다.  변환을 사용하면 프로젝트를 항목 목록으로 변환할 수 있을 뿐 아니라 대상을 통해 해당 입력과 출력 사이의 직접 매핑을 식별할 수 있습니다.  이 항목에는 변환과 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서 변환을 사용하여 프로젝트를 보다 효율적으로 빌드하는 방법에 대해 설명합니다.  
  
## 변환 한정자  
 변환은 임의로 수행되지 않고, 모든 변환 한정자가 %\(*ItemMetaDataName*\) 형식인 특별한 구문에 의해 한정됩니다.  모든 항목 메타데이터를 변환 한정자로 사용할 수 있습니다.  항목이 만들어질 때 모든 항목에 할당되는 잘 알려진 항목 메타데이터가 여기에 포함됩니다.  잘 알려진 항목 메타데이터 목록은 [Well\-known Item Metadata](../msbuild/msbuild-well-known-item-metadata.md)를 참조하십시오.  
  
 다음 예제에서는 .resx 파일 목록이 .resources 파일 목록으로 변환됩니다.  %\(filename\) 변환 한정자는 각 .resources 파일의 파일 이름이 해당 .resx 파일과 같도록 지정합니다.  
  
```  
@(RESXFile->'%(filename).resources')  
```  
  
> [!NOTE]
>  표준 항목 목록에 대해 구분 기호를 지정하는 것과 동일한 방법으로 변환된 항목 목록에 대해 사용자 지정 구분 기호를 지정할 수 있습니다.  예를 들어, 변환된 항목 목록을 기본 세미콜론\(;\) 대신 쉼표\(,\)로 구분하려면 다음 XML을 사용합니다.  
  
```  
@(RESXFile->'Toolset\%(filename)%(extension)', ',')  
```  
  
 예를 들어, @\(RESXFile\) 항목 목록의 항목이 `Form1.resx`, `Form2.resx` 및 `Form3.resx`인 경우 변환된 목록의 출력은 `Form1.resources`, `Form2.resources` 및 `Form3.resources`가 됩니다.  
  
## 여러 한정자 사용  
 변환 식에 여러 개의 한정자가 포함될 수 있습니다. 이때 한정자는 어떤 순서로도 조합될 수 있으며 반복될 수 있습니다.  다음 예제에서 파일이 들어 있는 디렉터리 이름은 변경되지만 파일의 원래 이름과 확장명은 그대로 유지됩니다.  
  
```  
@(RESXFile->'Toolset\%(filename)%(extension)')  
```  
  
 예를 들어, `RESXFile` 항목 목록에 포함된 항목이 `Project1\Form1.resx`, `Project1\Form2.resx` 및 `Project1\Form3.text`이면 변환된 목록의 출력은 `Toolset\Form1.resx`, `Toolset\Form2.resx` 및 `Toolset\Form3.text`가 됩니다.  
  
## 종속성 분석  
 변환된 항목 목록과 원래 항목 목록 사이에는 항상 일대일 매핑 관계가 있습니다.  따라서 대상이 입력의 변환인 출력을 만들면 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 입력과 출력의 타임스탬프를 분석하여 대상을 건너뛸지, 빌드할지 아니면 일부만 다시 빌드할지를 결정합니다.  
  
 다음 예제의 [Copy Task](../msbuild/copy-task.md)에서 `BuiltAssemblies` 항목 목록의 모든 파일은 `Outputs` 특성에 변환을 사용하여 지정된 작업의 대상 폴더에 있는 파일로 매핑됩니다.  `BuiltAssemblies` 항목 목록의 파일이 변경되면 `Copy` 작업은 변경된 파일에 대해서만 실행되고 다른 모든 파일은 건너뜁니다.  종속성 분석 및 변형 사용 방법에 대한 자세한 내용은 [방법: 증분 빌드](../msbuild/how-to-build-incrementally.md)를 참조하십시오.  
  
```  
<Target Name="CopyOutputs"  
    Inputs="@(BuiltAssemblies)"  
    Outputs="@(BuiltAssemblies -> '$(OutputPath)%(Filename)%(Extension)')">  
  
    <Copy  
        SourceFiles="@(BuiltAssemblies)"  
        DestinationFolder="$(OutputPath)"/>  
  
</Target>  
```  
  
## 예제  
  
### 설명  
 다음 예제에서는 변환을 사용하는 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트 파일을 보여 줍니다.  이 예제에서는 c:\\sub0\\sub1\\sub2\\sub3 디렉터리에 .xsd 파일 하나가 있고 작업 디렉터리는 c:\\sub0이라고 가정합니다.  
  
### 코드  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Schema Include="sub1\**\*.xsd"/>  
    </ItemGroup>  
  
    <Target Name="Messages">  
        <Message Text="rootdir: @(Schema->'%(rootdir)')"/>  
        <Message Text="fullpath: @(Schema->'%(fullpath)')"/>  
        <Message Text="rootdir + directory + filename + extension: @(Schema->'%(rootdir)%(directory)%(filename)%(extension)')"/>  
        <Message Text="identity: @(Schema->'%(identity)')"/>  
        <Message Text="filename: @(Schema->'%(filename)')"/>  
        <Message Text="directory: @(Schema->'%(directory)')"/>  
        <Message Text="relativedir: @(Schema->'%(relativedir)')"/>  
        <Message Text="extension: @(Schema->'%(extension)')"/>  
    </Target>  
</Project>  
```  
  
### 설명  
 이 예제의 결과는 다음과 같습니다.  
  
```  
rootdir: C:\  
fullpath: C:\xmake\sub1\sub2\sub3\myfile.xsd  
rootdir + directory + filename + extension: C:\xmake\sub1\sub2\sub3\myfile.xsd  
identity: sub1\sub2\sub3\myfile.xsd  
filename: myfile  
directory: xmake\sub1\sub2\sub3\  
relativedir: sub1\sub2\sub3\  
extension: .xsd  
```  
  
## 참고 항목  
 [MSBuild 개념](../msbuild/msbuild-concepts.md)   
 [MSBuild Reference](../msbuild/msbuild-reference.md)   
 [방법: 증분 빌드](../msbuild/how-to-build-incrementally.md)