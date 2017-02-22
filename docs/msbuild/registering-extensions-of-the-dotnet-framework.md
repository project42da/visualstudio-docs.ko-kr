---
title: ".NET Framework 확장 등록 | Microsoft Docs"
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
  - "참조 추가 대화 상자, .NET Framework 확장 등록"
  - "MSBuild, .NET Framework 확장 등록"
  - ".NET Framework 확장, 등록"
ms.assetid: deee6f53-ea87-4b88-a120-bea589822e03
caps.latest.revision: 5
caps.handback.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# .NET Framework 확장 등록
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

특정 버전의 .NET Framework를 확장하는 어셈블리를 개발할 수 있습니다.  Visual Studio **참조 추가** 대화 상자에 어셈블리가 표시되도록 하려면 시스템 레지스트리에 어셈블리가 들어 있는 폴더를 추가해야 합니다.  
  
 예를 들어 .NET Framework 4를 확장하는 라이브러리를 개발한 Trey Research라는 회사에서 프로젝트가 .NET Framework 4를 대상으로 하는 경우 해당 라이브러리 어셈블리가 **참조 추가** 대화 상자에 표시되기를 원한다고 가정합니다.  또한 어셈블리가 32비트 컴퓨터에서 실행되는 32비트 어셈블리이거나 64비트 컴퓨터에서 실행되는 64비트 컴퓨터이고 C:\\TreyResearch\\Extensions4\\ 폴더에 설치된다고 가정합니다.  
  
 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework\\v4.0.21006\\AssemblyFoldersEx\\TreyResearch\\ 키를 사용하여 이 폴더를 등록합니다.  이 키에 기본값인 C:\\TreyResearch\\Extensions4를 지정합니다.  
  
> [!NOTE]
>  .NET Framework 버전의 빌드 번호는 다를 수 있습니다.  
  
 64비트 컴퓨터에 32비트 어셈블리를 등록하려면 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\.NETFramework\\v4.0.21006\\AssemblyFoldersEx\\TreyResearch\\와 같이 Wow6432 노드를 사용합니다.  
  
## 참고 항목  
 [Visual Studio 통합](../msbuild/visual-studio-integration-msbuild.md)