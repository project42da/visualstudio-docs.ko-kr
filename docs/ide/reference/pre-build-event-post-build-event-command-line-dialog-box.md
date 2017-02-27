---
title: "빌드 전 이벤트/빌드 후 이벤트 명령줄 대화 상자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cs.ProjectPropertiesBuildEventsBuilder"
  - "vb.ProjectPropertiesBuildEventsBuilder"
helpviewer_keywords: 
  - "$(SolutionExt)"
  - "$(ProjectDir)"
  - "$(Targetpath)"
  - "$(ProjectExt)"
  - "$(TargetFileName)"
  - "$(PlatformName)"
  - "$(SolutionName)"
  - "매크로, 빌드 이벤트"
  - "$(SolutionPath)"
  - "$(ProjectPath)"
  - "$(ProjectFileName)"
  - "$(DevEnvDir)"
  - "$(Targetname)"
  - "$(Targetdir)"
  - "$(Solutiondir)"
  - "$(TargetExt)"
  - "$(OutDir)"
  - "$(ConfigurationName)"
  - "$(SolutionFileName)"
  - "$(ProjectName)"
  - "빌드 이벤트, 매크로"
ms.assetid: d49b2c57-24bf-4fb2-8351-5c4b6cca938f
caps.latest.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 13
---
# 빌드 전 이벤트/빌드 후 이벤트 명령줄 대화 상자
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[프로젝트 디자이너, 빌드 이벤트 페이지\(C\#\)](../../ide/reference/build-events-page-project-designer-csharp.md)에 대한 빌드 전 이벤트나 빌드 후 이벤트를 입력란에 직접 입력하거나, 사용할 수 있는 매크로 목록에서 빌드 전 매크로나 빌드 후 매크로를 선택할 수 있습니다.  
  
> [!NOTE]
>  빌드 전 이벤트는 프로젝트가 최신 상태이고 빌드가 트리거되지 않은 경우 실행되지 않습니다.  
  
## UI 요소 목록  
 **명령줄 편집 상자**  
 빌드 전이나 빌드 후에 실행할 이벤트를 포함합니다.  
  
> [!NOTE]
>  .bat 파일을 실행하는 모든 빌드 후 명령 앞에 `call` 문을 추가하십시오.  예를 들면 `call C:\MyFile.bat` 또는 `call C:\MyFile.bat call C:\MyFile2.bat`를 사용할 수 있습니다.  
  
 **매크로**  
 편집 상자를 확장하여 명령줄 편집 상자에 삽입할 매크로 목록을 표시합니다.  
  
 **매크로 테이블**  
 사용 가능한 매크로와 해당 값을 나열합니다.  각 매크로에 대한 설명은 아래에 있는 "매크로"를 참조하십시오.  한 번에 한 개의 매크로만 선택하여 명령줄 편집 상자에 삽입할 수 있습니다.  
  
 **Insert**  
 매크로 테이블에서 선택한 매크로를 명령줄 편집 상자에 삽입합니다.  
  
### 매크로  
 다음 매크로 중 하나를 사용하여 파일 위치를 지정할 수 있으며 여러 개의 파일이 선택 가능한 경우 입력 파일의 실제 이름을 가져올 수 있습니다.  이 매크로는 대\/소문자를 구분하지 않습니다.  
  
|매크로|설명|  
|---------|--------|  
|`$(ConfigurationName)`|현재 프로젝트 구성의 이름\(예: "Debug"\)입니다.|  
|`$(OutDir)`|출력 파일 디렉터리의 경로로서 프로젝트 디렉터리에 대해 상대적인 경로.  이 경로는 출력 디렉터리 속성의 값이 됩니다.  뒤에는 백슬래시\('\\'\)가 붙습니다.|  
|`$(DevEnvDir)`|\(드라이브와 경로로 정의\); Visual Studio 설치 디렉터리 후행 백슬래시를 포함 ' \\'.|  
|`$(PlatformName)`|현재 대상 플랫폼의 이름입니다.  예: "AnyCPU".|  
|`$(ProjectDir)`|드라이브와 경로로 정의되는 프로젝트의 디렉터리로, 뒤에는 백슬래시\(\\\)가 붙습니다.|  
|`$(ProjectPath)`|드라이브, 경로, 기본 이름 및 파일 확장명으로 정의되는 프로젝트의 절대 경로 이름입니다.|  
|`$(ProjectName)`|프로젝트의 기본 이름.|  
|`$(ProjectFileName)`|기본 이름과 파일 확장명으로 정의되는 프로젝트의 파일 이름입니다.|  
|`$(ProjectExt)`|프로젝트의 파일 확장명.  파일 확장명 앞에는 '.'이 붙습니다.|  
|`$(SolutionDir)`|드라이브와 경로로 정의되는 솔루션의 디렉터리로, 뒤에는 백슬래시\(\\\)가 붙습니다.|  
|`$(SolutionPath)`|드라이브, 경로, 기본 이름 및 파일 확장명으로 정의되는 솔루션의 절대 경로 이름입니다.|  
|`$(SolutionName)`|솔루션의 기본 이름.|  
|`$(SolutionFileName)`|기본 이름과 파일 확장명으로 정의되는 솔루션의 파일 이름입니다.|  
|`$(SolutionExt)`|솔루션의 파일 확장명.  파일 확장명 앞에는 '.'이 붙습니다.|  
|`$(TargetDir)`|드라이브와 경로로 정의되는 빌드용 기본 출력 파일의 디렉터리입니다.  뒤에는 백슬래시\('\\'\)가 붙습니다.|  
|`$(TargetPath)`|드라이브, 경로, 기본 이름 및 파일 확장명으로 정의되는 빌드용 기본 출력 파일의 절대 경로 이름입니다.|  
|`$(TargetName)`|빌드용 기본 출력 파일의 기본 이름.|  
|`$(TargetFileName)`|기본 이름과 파일 확장명으로 정의되는 빌드용 기본 출력 파일의 파일 이름입니다.|  
|`$(TargetExt)`|빌드용 기본 출력 파일의 파일 확장명.  파일 확장명 앞에는 '.'이 붙습니다.|  
  
## 참고 항목  
 [Visual Studio에서 사용자 지정 빌드 이벤트 지정](../../ide/specifying-custom-build-events-in-visual-studio.md)   
 [프로젝트 디자이너, 빌드 이벤트 페이지\(C\#\)](../../ide/reference/build-events-page-project-designer-csharp.md)   
 [방법: 빌드 이벤트 지정\(Visual Basic\)](../../ide/how-to-specify-build-events-visual-basic.md)   
 [방법: 빌드 이벤트 지정\(C\#\)](../../ide/how-to-specify-build-events-csharp.md)