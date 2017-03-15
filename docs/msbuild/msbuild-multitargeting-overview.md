---
title: "MSBuild 멀티 타기팅 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eecbcd65-9fbc-4307-a321-46d3c3b79b12
caps.latest.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 10
---
# MSBuild 멀티 타기팅 개요
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

MSBuild를 사용하면 .NET Framework 여러 버전 또는 여러 시스템 플랫폼 중 하나에서 실행되는 응용 프로그램을 컴파일할 수 있습니다.  예를 들어 32비트 플랫폼의 .NET Framework 2.0에서 실행되도록 응용 프로그램을 컴파일하고 동일한 응용 프로그램을 64비트 플랫폼의 .NET Framework 4.5에서 실행되도록 컴파일할 수 있습니다.  
  
> [!IMPORTANT]
>  "다중" 임에도 불구하고 프로젝트는 한번에 하나의 프레임 워크 및 플랫폼 하나만 지정할 수 있습니다.  
  
 이것들이 MSBuild를 대상으로 하는 일부 기능입니다.  
  
-   이전 .NET Framework 버전, 예를들어 2.0, 3.5, 그리고 4 버전을 대상으로 하는 응용 프로그램을 개발할 수 있습니다.  
  
-   .NET Framework 외에 Silverlight 프레임워크 같이 다른 프레임워크를 대상으로 지정할 수 있습니다.  
  
-   대상 프레임워크의 미리 정의된 하위 집합인 *프레임워크 프로필*을 대상으로 지정할 수 있습니다.  
  
-   현재 버전의 .NET Framework용 서비스 팩이 릴리스될 경우 해당 서비스 팩을 대상으로 지정할 수 있습니다.  
  
-   MSBuild 대상 지정은 응용 프로그램이 지정된 프레임워크 및 플랫폼에서 사용 가능한 기능을 사용할수 있도록 보장합니다.  
  
## 대상 프레임워크 및 플랫폼  
 *대상 프레임워크* 는 실행할 프로젝트를 빌드할 수 있는 .NET Framework 버전이고, *대상 플랫폼* 은 실행할 프로젝트를 빌드할 수 있는 시스템 플랫폼을 말합니다.  예를들면, 사용자는 802 x 86 프로세서 제품군\("x86"\)와 호환 되는 32 비트 플랫폼의 .NET Framework 2.0에서 실행 되도록 응용 프로그램을 지정하고 싶을수 있습니다.  대상 프레임 워크와 대상 플랫폼의 조합을 *대상 컨텍스트* 라고 부릅니다.  자세한 내용은 [대상 프레임워크 및 대상 플랫폼](../msbuild/msbuild-target-framework-and-target-platform.md)을 참조하십시오.  
  
## 도구 집합\(ToolsVersion\)  
 도구 집합은 응용 프로그램을 만드는데 사용되는 도구, 작업 및 대상들을 함께 수집해 줍니다.  도구 집합에는 csc.exe 및 vbc.exe 같은 컴파일러, 일반 대상 파일\(microsoft.common.targets\) 및 일반 작업 파일\(microsoft.common.tasks\)이 포함됩니다.  4.5 도구 집합은 .NET Framework 2.0, 3.0, 3.5, 4, 4.5 버전을 대상으로 사용될 수 있습니다. However, the 2.0 Toolset can only be used to target the .NET Framework version 2.0.  자세한 내용은 [도구 집합\(ToolsVersion\)](../msbuild/msbuild-toolset-toolsversion.md)을 참조하십시오.  
  
## 참조 어셈블리  
 도구 집합에 지정된 참조 어셈블리는 응용 프로그램을 설계 및 구축하는데 도움이 됩니다.  These reference assemblies not only enable a particular target build, but also restrict components and features in the Visual Studio IDE to those that are compatible with the target.  자세한 내용은 [디자인 타임에 어셈블리 확인](../msbuild/resolving-assemblies-at-design-time.md)을 참조하십시오.  
  
## 대상 및 작업 구성  
 사용자는 MSBuild를 사용하여 현재 실행하고 있는 컨텍스트와는 완전히 다른 컨텍스트를 대상으로 지정하기 위해서 MSBuild 대상 및 작업을 out\-of\-process 상태로 실행되도록 구성할 수 있습니다.  예를 들어, 개발 컴퓨터가 64비트 플랫폼 및 .NET Framework 4.5 환경에서 실행되는 동안 32비트 .NET Framework 2.0 응용 프로그램을 대상으로 지정할 수 있습니다. 자세한 내용은 [대상 및 작업 구성](../msbuild/configuring-targets-and-tasks.md)을 참조하십시오.  
  
## 문제 해결  
 대상 컨텍스트가 아닌 어셈블리를 참조 하려고 하면 오류가 발생할 수 있습니다.  이러한 오류와 그 대처법에 대한 자세한 내용은 [.NET Framework 대상 지정 오류 문제 해결](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md) 을 참조하십시오.