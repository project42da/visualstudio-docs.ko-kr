---
title: "방법: 빌드 로그 파일 보기, 저장 및 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 75d38b76-26d6-4f43-bbe7-cbacd7cc81e7
caps.latest.revision: 7
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 7
---
# 방법: 빌드 로그 파일 보기, 저장 및 구성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio IDE에서 프로젝트를 빌드한 후 해당 빌드에 대 한 정보를 볼 수 있는  **출력** 창.  이 정보를 사용 하 여 예를 들어, 빌드 실패를 해결할 수 있습니다.  C \+ \+ 프로젝트에 대해 작성 하 고 자동으로 저장 된.txt 파일에 동일한 정보를 볼 수도 있습니다.  관리 코드 프로젝트에 대 한 복사 및 정보를 붙여 넣을 수 있습니다의  **출력** 창에.txt 파일과 직접 저장 합니다.  IDE를 사용 하면 각 빌드에 대 한 표시 하려는 정보의 종류를 지정할 수 있습니다.  
  
 Msbuild를 사용 하 여 모든 종류의 프로젝트를 빌드하는 경우 빌드에 대 한 정보를 저장 하려면.txt 파일을 만들 수 있습니다.  자세한 내용은 [빌드 로그 가져오기](../msbuild/obtaining-build-logs-with-msbuild.md)을 참조하십시오.  
  
### C \+ \+ 프로젝트에 대 한 빌드 로그 파일을 보려면  
  
1.  **Windows 탐색기** 또는  **파일 탐색기**, 다음 파일을 엽니다. \\...  \\Visual studio  *버전*\\Projects\\*ProjectName*\\*ProjectName*\\Debug\\*ProjectName*.txt  
  
### 관리 코드 프로젝트에 대 한 빌드 로그 파일을 만들려면  
  
1.  메뉴 모음에서 선택  **빌드**,  **솔루션 빌드**.  
  
2.  에  **출력** 창에서 빌드 정보를 강조 표시 한 다음 클립보드에 복사 합니다.  
  
3.  메모장과 같은 텍스트 편집기를 열고, 정보를 파일에 붙여 및 다음 저장 합니다.  
  
### 빌드 로그에 포함 된 정보의 양 변경  
  
1.  메뉴 모음에서 선택  **도구**,  **옵션**.  
  
2.  에  **프로젝트 및 솔루션** 페이지에서 선택 된  **빌드 및 실행** 페이지.  
  
3.  에  **MSBuild 프로젝트 빌드 출력의 자세한 정도** 목록에서 다음 값 중 하나를 선택 하 고 다음 선택의  **확인** 단추.  
  
    |정도|설명|  
    |--------|--------|  
    |최소|만 빌드 요약을 표시 합니다.|  
    |약간|빌드 및 오류, 경고 및 메시지는 분류 되는 요약으로 매우 중요 한 표시 합니다.|  
    |Normal|빌드 요약을 표시합니다. 오류, 경고 및 매우 중요 한으로 분류 된 메시지입니다. 및 빌드의 주요 단계입니다.  이 수준의 세부 정보를 가장 자주 사용 됩니다.|  
    |자세히|빌드 요약을 표시합니다. 오류, 경고 및 매우 중요 한으로 분류 된 메시지입니다. 모든 단계는 빌드. 및 중요도 기준으로 분류 된 메시지입니다.|  
    |매우 자세히|빌드에 사용할 수 있는 모든 데이터를 표시 합니다.  사용자 지정 빌드 스크립트 문제 및 기타 빌드 문제를 디버깅 하는 데이 수준의 세부 정보를 사용할 수 있습니다.|  
  
     자세한 내용은 [옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행](../ide/reference/options-dialog-box-projects-and-solutions-build-and-run.md) 및 <xref:Microsoft.Build.Framework.LoggerVerbosity>을 참조하십시오.  
  
    > [!IMPORTANT]
    >  변경 내용 적용 하기 위한 프로젝트를 다시 빌드해야 합니다의  **출력** \(모든 프로젝트의 경우\) 창 고  *ProjectName*.txt 파일 \(c \+ \+ 프로젝트에만 해당\).  
  
## 참고 항목  
 [빌드 로그 가져오기](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [Visual Studio에서 프로젝트 및 솔루션 빌드 및 정리](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [Visual Studio에서 응용 프로그램　빌드](../ide/compiling-and-building-in-visual-studio.md)