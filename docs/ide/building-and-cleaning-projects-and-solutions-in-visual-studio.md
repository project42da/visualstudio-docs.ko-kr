---
title: "Visual Studio에서 프로젝트 및 솔루션 빌드 및 정리 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.BuildProjectPicker"
  - "vs.batchbuild"
helpviewer_keywords: 
  - "솔루션 정리 명령"
  - "빌드[Visual Studio], 관리"
  - "솔루션 빌드 구성, 시작"
  - "솔루션 빌드 명령"
  - "프로젝트 빌드 구성, 시작"
  - "빌드 구성, 시작"
  - "프로젝트 빌드 구성, 종속성"
  - "솔루션 다시 빌드 명령"
  - "솔루션 빌드 구성, 빌드 순서"
  - "빌드[Visual Studio], 준비"
ms.assetid: 710891fd-379e-42c2-a84b-44a7af694ca0
caps.latest.revision: 35
caps.handback.revision: 35
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# Visual Studio에서 프로젝트 및 솔루션 빌드 및 정리
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 항목의 절차를 사용 하 여 빌드 다시 빌드 또는 프로젝트 또는 솔루션의 프로젝트 항목의 전부 또는 일부를 정리할 수 있습니다.  에 대 한 단계별 자습서를 참조 하십시오. [연습: 응용 프로그램 빌드](../ide/walkthrough-building-an-application.md).  
  
> [!NOTE]
>  이 항목을 현재 설정에 따라 설명에서 UI에 Visual Studio 버전에 따라 달라질 수 있습니다.  열 설정을 변경 하는  **도구** 메뉴에서 다음 선택  **설정 가져오기 및 내보내기**.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 전체 솔루션을 빌드, 다시 빌드 또는 정리하려면  
  
1.  **솔루션 탐색기**, 선택 또는 솔루션을 엽니다.  
  
2.  메뉴 표시줄에서 선택  **빌드**, 후 다음 명령 중 하나를 선택 합니다.  
  
    -   선택  **빌드** 또는  **솔루션 빌드** 는 파일 및 구성 요소는 가장 최근 빌드 이후 변경 된 프로젝트만 컴파일합니다.  
  
        > [!NOTE]
        >  솔루션에 프로젝트가 여러 개 포함된 경우에는 **빌드** 명령이 **솔루션 빌드** 명령으로 바뀝니다.  
  
    -   선택  **솔루션 다시 빌드** "솔루션 정리" 한 다음 모든 프로젝트 파일과 구성 요소를 작성 합니다.  
  
    -   선택  **솔루션 정리** 중간 파일과 출력 파일을 모두 삭제 합니다.  프로젝트와 구성 요소 파일만에 왼쪽, 중간의 새 인스턴스 및 출력 파일 다음 빌드할 수 있습니다.  
  
### 프로젝트 하나를 빌드 또는 다시 빌드하려면  
  
1.  **솔루션 탐색기**, 선택 또는 프로젝트를 엽니다.  
  
2.  메뉴 모음에서 선택  **빌드**를 다음 중 하나를 선택 하 고  **빌드***ProjectName* 또는  **다시***ProjectName*.  
  
    -   선택  **빌드***ProjectName* 는 가장 최근 빌드 이후 변경 된 구성 프로젝트만 빌드할 수 있습니다.  
  
    -   선택  **를 다시***ProjectName* 프로젝트를 "정리" 한 다음 프로젝트 파일과 모든 프로젝트 구성 요소를 작성 합니다.  
  
### 시작 프로젝트와 프로젝트의 종속성만 빌드하려면  
  
1.  메뉴 모음에서 선택  **도구**,  **옵션**.  
  
2.  에  **옵션** 대화 상자에서 확장은  **프로젝트 및 솔루션** 노드를 다음 선택은  **빌드 및 실행** 페이지.  
  
     **빌드 및 실행 옵션, 프로젝트 및 솔루션** 대화 상자가 열립니다.  
  
3.  선택 된  **실행에 대 한 종속성 및 시작 프로젝트만 빌드** 확인란을 선택 합니다.  
  
     이 확인란을 선택 하면 다음 단계 중 하나를 수행 하는 경우 현재 시작 프로젝트와 해당 종속성 구축 됩니다.  
  
    -   메뉴 모음에서 선택  **디버깅**,  **시작** \(f5 키\).  
  
    -   메뉴 모음에서 선택  **빌드**,  **솔루션 빌드** \(CTRL \+ SHIFT \+ B\).  
  
     이 확인란을 선택 하지 않으면 앞의 명령 중 하나를 실행 하면 모든 프로젝트, 프로젝트의 종속성 및 솔루션 파일이 빌드됩니다.  이 확인란은 기본적으로 선택되어 있지 않습니다.  
  
### 선택한 Visual C\+\+ 프로젝트만 빌드하려면  
  
1.  선택 된 [!INCLUDE[vcprvc](../debugger/includes/vcprvc_md.md)] 프로젝트를 누른 다음 메뉴 모음에서를 선택  **빌드**,  **프로젝트만**, 및 다음 명령 중 하나:  
  
    -   **만 빌드** *프로젝트 이름*  
  
    -   **만 다시 빌드** *프로젝트 이름*  
  
    -   **정리만** *프로젝트 이름*  
  
    -   **만 링크** *프로젝트 이름*  
  
     이러한 명령에만 적용 된 [!INCLUDE[vcprvc](../debugger/includes/vcprvc_md.md)] 구축, 재구축, 정리, 또는 프로젝트 종속성 또는 솔루션 파일을 연결 하지 않고 선택한 프로젝트입니다.  버전에 따라 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)],  **프로젝트만** 하위 메뉴 추가 명령도 포함 될 수 있습니다.  
  
### 여러 C\+\+ 프로젝트 항목을 컴파일하려면  
  
1.  **솔루션 탐색기**에 여러 파일이 컴파일된 작업 수를 선택 합니다. 이러한 파일 중 하나에 대 한 바로 가기 메뉴를 열고 선택  **컴파일**.  
  
     파일 종속성이 없는 경우 파일 종속성 순서에 컴파일됩니다.  컴파일하는 경우에 사용할 수 없는 미리 컴파일된 헤더 파일을 필요로 하는 경우 컴파일 작업이 실패 합니다.  현재 활성 솔루션 구성을 컴파일 작업을 사용합니다.  
  
### 빌드를 중지하는 방법  
  
1.  다음 단계 중 하나를 수행합니다.  
  
    -   메뉴 모음에서 선택  **빌드**,  **취소**.  
  
    -   선택 Ctrl \+ 키를 중단 합니다.  
  
## 참고 항목  
 [방법: 빌드 로그 파일 보기, 저장 및 구성](../ide/how-to-view-save-and-configure-build-log-files.md)   
 [빌드 로그 가져오기](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [Visual Studio에서 응용 프로그램　빌드](../ide/compiling-and-building-in-visual-studio.md)   
 [빌드 구성 이해](../ide/understanding-build-configurations.md)   
 [Debug and Release Project Configurations](http://msdn.microsoft.com/ko-kr/0440b300-0614-4511-901a-105b771b236e)   
 [C\/C\+\+ 빌드 참조](/visual-cpp/build/reference/c-cpp-building-reference)   
 [Devenv 명령줄 스위치](../ide/reference/devenv-command-line-switches.md)   
 [솔루션 및 프로젝트](../ide/solutions-and-projects-in-visual-studio.md)