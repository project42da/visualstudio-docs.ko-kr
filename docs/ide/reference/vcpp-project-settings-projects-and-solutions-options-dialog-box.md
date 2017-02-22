---
title: "옵션 대화 상자, 프로젝트 및 솔루션, VC++ 프로젝트 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.ToolsOptionsPages.Projects.VCBuild"
helpviewer_keywords: 
  - "빌드[Visual Studio], 로그"
  - "빌드 프로세스[C++]"
  - "파일[Visual Studio], C/C++ 컴파일러로 작성"
  - "파일 확장명, C 또는 C++ 컴파일러로 작성"
  - "cl.exe 컴파일러, 파일 확장명"
  - "확장명, C 또는 C++ 컴파일러로 작성된 파일"
  - "BuildLog.htm"
ms.assetid: 56420efd-6a95-464e-b890-e2b38c48d66a
caps.latest.revision: 15
caps.handback.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 옵션 대화 상자, 프로젝트 및 솔루션, VC++ 프로젝트 설정
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 대화 상자를 사용하여 빌드 로깅 및 지원 파일 형식과 관련된 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 프로젝트 설정을 정의할 수 있습니다.  
  
### 이 대화 상자에 액세스하려면  
  
1.  **도구** 메뉴에서 **옵션**을 클릭합니다.  
  
2.  **프로젝트 및 솔루션**을 선택한 다음 **VC\+\+ 프로젝트 설정**을 선택합니다.  
  
## 빌드 사용자 지정 검색 경로  
 프로젝트에 대한 빌드 규칙을 정의하는 데 도움이 되는 .rules 파일이 있는 디렉터리 목록을 지정합니다.  
  
## 빌드 로깅  
 **예**  
 빌드 로그 파일이 생성되도록 설정합니다.  이 옵션을 선택하면 BuildLog.htm이 만들어지며 이 파일은 프로젝트의 중간 파일 디렉터리에서 찾을 수 있습니다.  새로운 빌드는 이전의 BuildLog.htm 파일을 덮어씁니다.  
  
 **아니요**  
 빌드 로그 파일이 생성되지 않도록 설정합니다.  
  
## 빌드 타이밍  
 **예**  
 빌드 타이밍을 설정합니다.  이 옵션을 선택하면 빌드를 완료하는 데 걸리는 시간이 출력 창에 나타납니다.  자세한 내용은 [출력 창](../../ide/reference/output-window.md)을 참조하십시오.  
  
 **아니요**  
 빌드 타이밍을 해제합니다.  
  
## 숨길 확장명  
 **모든 파일 표시**가 활성화된 경우 **솔루션 탐색기**에 표시하지 않을 파일의 파일 확장명을 지정합니다.  
  
## 포함할 확장명  
 프로젝트로 이식될 수 있는 파일의 파일 확장명을 지정합니다.  
  
## 최대 동시 C\+\+ 컴파일 수  
 병렬 C\+\+ 컴파일에 사용할 최대 CPU 코어 수를 지정합니다.  
  
## 로그에 환경 표시  
 **예**  
 빌드 로그 파일에 있는 환경 변수를 나열합니다.  이 옵션은 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 프로젝트를 빌드하는 동안 모든 환경 변수를 빌드 로그 파일에 표시하도록 지정합니다.  
  
 **아니요**  
 빌드 로그 파일에서 환경 변수를 제외합니다.  
  
## 솔루션 탐색기 모드  
 **프로젝트에 포함된 파일만 표시**  
 프로젝트에 있는 파일만 표시하도록 **솔루션 탐색기**를 구성합니다.  
  
 **모든 파일 표시**  
 프로젝트에 있는 파일과 디스크의 프로젝트 폴더에 있는 파일을 표시하도록 **솔루션 탐색기**를 구성합니다.  
  
## 참고 항목  
 [C\/C\+\+ 프로그램 빌드](/visual-cpp/build/building-c-cpp-programs)   
 [C\/C\+\+ 빌드 참조](/visual-cpp/build/reference/c-cpp-building-reference)