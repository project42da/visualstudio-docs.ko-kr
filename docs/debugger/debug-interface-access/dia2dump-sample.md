---
title: "Dia2dump 샘플 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "샘플 응용 프로그램[DIA SDK]"
  - "Dia2dump 샘플[DIA SDK]"
ms.assetid: 492c0893-7043-452f-a020-890a47230d20
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Dia2dump 샘플
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Dia2dump 샘플 Visual Studio 설치 되 고 Dia2dump.cpp 소스 파일을 포함 합니다.  컴파일된 실행 파일 명령줄에서 실행 되 고 전체 프로그램 데이터베이스 \(.pdb\) 파일의 내용을 표시 합니다.  
  
### 샘플을 설치 하려면  
  
1.  시스템 Visual Studio 설치 시작 페이지에서 설명 하는 모든 설치 요구 사항을 충족 하는지 확인 하십시오.  
  
2.  Visual Studio 설치 하 고 포함 된 예제에 대 한 모든 설정 및 설치 지침을 따릅니다.  
  
#### 이 샘플을 빌드하려면  
  
1.  Visual Studio Dia2dump.sln 파일을 엽니다.  \(필요 하다 면 Visual Studio 먼저 Dia2dump 프로젝트 업그레이드 도와줍니다.\)  
  
2.  프로젝트 속성 페이지에서에 있는  **C\/C\+\+** &#124; **일반** &#124; **추가 포함 디렉터리** 속성으로 지정은  `.\DIA SDK\include` 디렉터리.  이렇게 컴파일러가 dia2.h 파일을 찾을 수 있습니다.  
  
3.  **빌드** 메뉴에서 **솔루션 다시 빌드**를 클릭합니다.  
  
4.  Visual Studio 닫습니다.  
  
#### 이 샘플을 실행하려면  
  
1.  명령 프롬프트를 열고 다음을 입력 합니다.  
  
    ```  
    dia2dump filename  
    ```  
  
## 참고 항목  
 [Dia2dump.cpp 소스 파일](../../debugger/debug-interface-access/dia2dump-cpp-source-file.md)   
 [방법: 실패한 Visual Studio 프로젝트 업그레이드 문제 해결](../../porting/how-to-troubleshoot-unsuccessful-visual-studio-project-upgrades.md)