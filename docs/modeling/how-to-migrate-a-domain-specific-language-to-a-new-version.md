---
title: "방법: 도메인별 언어를 새 버전으로 마이그레이션 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a1ae073-443e-45ca-8bc9-9b944362b449
caps.latest.revision: 14
author: alancameronwills
ms.author: awills
manager: douge
translationtype: Machine Translation
ms.sourcegitcommit: 3d07f82ea737449fee6dfa04a61e195654ba35fa
ms.openlocfilehash: 397efd1049ea52b2e7c67a46509d2a088c6fa488
ms.lasthandoff: 02/22/2017

---
# <a name="how-to-migrate-a-domain-specific-language-to-a-new-version"></a>방법: 도메인별 언어를 새 버전으로 마이그레이션
정의 및 도메인별 언어를 사용 하는 프로젝트를 마이그레이션할 수 있는 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] 버전의 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] 하는 배포 된 [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)]합니다.  
  
 마이그레이션 도구가의 일부로 제공 됩니다 [!INCLUDE[vssdk_current_long](../misc/includes/vssdk_current_long_md.md)]합니다. 변환 도구 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트 및 솔루션을 사용 하거나 DSL 도구를 정의 합니다.  
  
 마이그레이션 도구를 명시적으로 실행 해야 합니다:에서 솔루션을 열 때 자동으로 시작 되지 않은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 도구 및 자세한 지침 문서가이 경로에서 찾을 수 있습니다.  
  
 **% Program Files%\Microsoft Visual Studio 2010 SDK\VisualStudioIntegration\Tools\DSLTools\DslProjectsMigrationTool.exe**  
  
## <a name="before-you-migrate-your-dsl-projects"></a>DSL 프로젝트 마이그레이션 전에  
 마이그레이션 도구는 수정 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트 파일 (**.csproj**) 및 솔루션 파일 (**.sln**).  
  
#### <a name="to-prepare-projects-for-migration"></a>마이그레이션에 대 한 프로젝트를 준비 합니다.  
  
-   확인은 **.csproj** 및 **.sln** 파일을 쓸 수 있습니다. 동일한 소스 제어에서 사용 중인 경우 선택 되어 있는지 확인 합니다.  
  
-   마이그레이션할지 폴더의 복사본을 만듭니다.  
  
## <a name="migrating-a-collection-of-projects"></a>프로젝트의 컬렉션 마이그레이션  
  
#### <a name="to-migrate-dsl-projects-and-solutions-to-visual-studio-2010"></a>Visual Studio 2010 DSL 프로젝트 및 솔루션 마이그레이션  
  
1.  DSL 마이그레이션 도구를 시작 합니다.  
  
    -   Windows 탐색기 (또는 파일 탐색기)의 도구를 두 번 클릭 하거나 명령 프롬프트에서이 도구를 시작할 수 있습니다. 이 도구는이 위치에 있습니다.  
  
         **%ProgramFiles%\Microsoft visual Studio 2010 SDK\VisualStudioIntegration\Tools\DSLTools\DslProjectsMigrationTool.exe**  
  
2.  솔루션 및 변환 하려는 프로젝트를 포함 하는 폴더를 선택 합니다.  
  
    -   도구를 맨 위에 있는 상자에 경로 입력 하거나 클릭 **찾아보기**합니다.  
  
     마이그레이션 도구 또는 Dsl을 사용 하 여 정의 하는 프로젝트의 트리를 표시 합니다. 사용 하는 모든 프로젝트를 포함 하는 트리는 **Microsoft.VisualStudio.Modeling.Sdk** 또는 **TextTemplating** 어셈블리입니다.  
  
3.  프로젝트의 트리를 검토 하 고 프로젝트를 변환 하려면 선택을 취소 합니다.  
  
    -   프로젝트 또는 도구 있도록 변경 작업의 목록을 보려면 솔루션을 선택 합니다.  
  
        > [!NOTE]
        >  폴더 이름 옆에 있는 확인란은 아무런 효과가 없습니다. 프로젝트 및 솔루션을 검사 하는 폴더를 확장 해야 합니다.  
  
4.  프로젝트를 변환 합니다.  
  
    1.  클릭 **변환**합니다.  
  
         복사본을 각 프로젝트 파일 변환 전에 *프로젝트***.csproj** 으로 저장 됩니다. *프로젝트***. vs2008.csproj**  
  
         각 복사본을 *솔루션***.sln** 으로 저장 됩니다. *솔루션***. vs2008.sln**  
  
    2.  보고 되는 모든 변환 실패를 조사 합니다.  
  
         오류는 텍스트 창에 보고 됩니다. 또한 트리 보기는 변환에 실패 했다는 각 노드에 빨간색 플래그를 표시 합니다. 해당 오류에 대 한 자세한 정보를 보려면 노드를 클릭 수 있습니다.  
  
5.  **모든 템플릿 변환** 성공적으로 포함 된 솔루션에서 프로젝트 변환 합니다.  
  
    1.  솔루션을 엽니다.  
  
    2.  클릭 된 **모든 템플릿 변환** 솔루션 탐색기의 헤더에는 단추입니다.  
  
        > [!NOTE]
        >  이 단계는 불필요 한으로 만들 수 있습니다. 자세한 내용은 참조 [모든 템플릿 변환 자동화 하는 방법을](http://msdn.microsoft.com/en-us/b63cfe20-fe5e-47cc-9506-59b29bca768a)합니다.  
  
6.  변환 된 프로젝트에서 사용자 지정 코드를 업데이트 합니다.  
  
    -   프로젝트를 빌드하고 오류가 있는지 조사 하려고 합니다.  
  
    -   디자이너를 테스트 합니다.  
  

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="see-also"></a>참고 항목  
 [관련된 블로그 게시물](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)

