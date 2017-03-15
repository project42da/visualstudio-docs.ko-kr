---
title: "대상 및 작업 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9aabe67a-1720-4bbf-80d3-822b3ccf75c0
caps.latest.revision: 6
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 6
---
# 대상 및 작업 구성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

사용자는 MSBuild를 사용하여 현재 실행하고 있는 컨텍스트와는 다른 컨텍스트를 대상으로 지정하기 위해서 MSBuild 대상 및 작업을 out\-of\-process 상태로 실행되도록 구성할 수 있습니다.  예를 들어, 개발 컴퓨터가 64비트 .NET Framework 4.5 운영 체제에서 실행되는 동안 32비트 .NET Framework 2.0 응용 프로그램을 대상으로 지정할 수 있습니다.  또한 .NET Framework 4 또는 이전 버전을 실행 하는 컴퓨터를 대상으로 지정할 수 있습니다.  32 또는 64 비트 및 특정 .NET Framework 버전의 조합은 *대상 컨텍스트*로 알려져 있습니다.  
  
## 설치  
 .NET Framework 4.5 및 4.5.1은 공용 언어 런타임 \(CLR\), 대상, 작업 및 .NET Framework 4의 도구를 이름을 바꾸지 않고 대체 합니다.  .NET Framework 4.5.1이 [!INCLUDE[vs_dev12](../data-tools/includes/vs_dev12_md.md)]의 부분으로 설치됩니다.  
  
 Visual Studio와 개별적으로 MSBuild를 설치 하려면, 설치 패키지를 [MSBuild 다운로드](http://go.microsoft.com/fwlink/?LinkId=309745)에서 다운로드 할 수 있습니다.  또한 사용자가 사용하기 원하는 .NET Framework 버전도 설치 해야 합니다.  
  
## 대상 및 작업  
 MSBuild는 더 큰 컨텍스트 집합을 대상으로 하기 위해 프로세스 밖 특정 작업을 실행합니다.  예를 들어, 64 비트 컴퓨터를 대상으로 지정하기 위해 64 비트 프로세스에서 32 비트 MSBuild 빌드 작업을 실행할 수 있습니다.  이것은 `UsingTask` 인수 및 `Task` 매개 변수에 의해 제어됩니다.  .NET Framework 4.5 집합에 의해 설치된 대상은 이러한 인수와 매개변수를 설정하고, 다양한 대상 컨텍스트를 위한 응용 프로그램을 변경할 필요가 없습니다.  
  
 사용자만의 대상 컨텍스트를 작성 하려는 경우, 이러한 인수와 매개 변수를 적절하게 설정해야 합니다.  .NET Framework 4.5 Microsoft.Common.targets 파일과 Microsoft.Common.Tasks 파일에 대한 예제를 살펴봅니다.  여러 대상 컨텍스트를 사용하여 작업할 수 있는 사용자 지정 작업 만들기 또는 기존 작업을 수정하는 방법에 대한 자세한 내용은 다음을 참조하십시오. [방법: 대상 및 작업 구성](../msbuild/how-to-configure-targets-and-tasks.md).  
  
## 참고 항목  
 [멀티 타기팅](../msbuild/msbuild-multitargeting-overview.md)