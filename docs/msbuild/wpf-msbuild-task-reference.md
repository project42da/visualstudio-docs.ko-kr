---
title: "WPF MSBuild Task Reference | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "WPF MSBuild task reference [WPF MSBuild], term/definition table"
  - "build tasks [WPF MSBuild], Microsoft build engine"
  - "build tasks using the Microsoft build engine [WPF MSBuild], compile markup and process resources"
  - "WPF MSBuild task reference [WPF MSBuild]"
ms.assetid: 96df0370-e50f-4ffc-9771-b12fb8721143
caps.latest.revision: 4
caps.handback.revision: 4
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# WPF MSBuild Task Reference
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

WPF\(Windows Presentation Foundation\) 빌드 프로세스는 태그 및 프로세스 리소스를 컴파일하는 작업을 비롯한 추가 빌드 작업 집합으로 Microsoft 빌드 엔진\(MSBuild\)을 확장합니다.  
  
## 단원 내용  
 [FileClassifier](../msbuild/fileclassifier-task.md)  
 어셈블리에 포함될 소스 리소스 집합을 분류합니다.  지역화할 수 없는 리소스는 주 응용 프로그램 어셈블리에 포함되고 지역화할 수 있는 어셈블리는 위성 어셈블리에 포함됩니다.  
  
 [GenerateTemporaryTargetAssembly](../msbuild/generatetemporarytargetassembly-task.md)  
 프로젝트에서 적어도 하나의 [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] 페이지가 해당 프로젝트에 로컬로 선언된 형식을 참조하는 경우 어셈블리를 생성합니다.  빌드 프로세스가 완료되거나 실패하면 생성된 어셈블리가 제거됩니다.  
  
 [GetWinFXPath](../msbuild/getwinfxpath-task.md)  
 현재 [!INCLUDE[TLA#tla_winfx](../msbuild/includes/tlasharptla_winfx_md.md)] 런타임의 디렉터리를 반환합니다.  
  
 [MarkupCompilePass1](../msbuild/markupcompilepass1-task.md)  
 지역화할 수 없는 [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] 프로젝트 파일을 컴파일된 이진 형식으로 변환합니다.  
  
 [MarkupCompilePass2](../msbuild/markupcompilepass2-task.md)  
 같은 프로젝트의 형식을 참조하는 [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] 파일에 대해 두 번째 패스 태그 컴파일을 수행합니다.  
  
 [MergeLocalizationDirectives](../msbuild/mergelocalizationdirectives-task.md)  
 하나 이상의 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 이진 형식 파일의 지역화 특성 및 주석을 전체 어셈블리에 대한 단일 파일로 병합합니다.  
  
 [ResourcesGenerator](../msbuild/resourcesgenerator-task.md)  
 하나 이상의 리소스\(이진 형식의 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)], .jpg, .ico, .bmp 및 기타 확장 형식\)를 .resources 파일에 포함합니다.  
  
 [UidManager](../msbuild/uidmanager-task.md)  
 소스 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일에 포함된 모든 [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] 요소를 지역화하기 위해 UID\(고유 ID\)를 확인하거나, 업데이트하거나, 제거합니다.  
  
 [UpdateManifestForBrowserApplication](../msbuild/updatemanifestforbrowserapplication-task.md)  
 [!INCLUDE[TLA#tla_xbap](../msbuild/includes/tlasharptla_xbap_md.md)] 프로젝트를 빌드할 때 응용 프로그램 매니페스트\(*projectname*.exe.manifest\)에  **\<hostInBrowser\/\>** 요소를 추가합니다.  
  
## 참고 항목  
 [MSBuild](http://msdn.microsoft.com/ko-kr/7c49aba1-ee6c-47d8-9de1-6f29a906e20b)