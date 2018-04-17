---
title: 솔루션에 대 한 부모 컨테이너 폴더를 만드는 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- solutions, creating parent containers
- source control plug-ins, creating parent containers
ms.assetid: 961e68ed-2603-4479-a306-330eda2b2efa
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2104c0c109db0d410cbd08683ce227c62982fd65
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-parent-container-folders-for-solutions"></a>솔루션에 대 한 부모 컨테이너 폴더 만들기
소스 제어 플러그 인 API 버전 1.2에서에서 사용자 솔루션 내에서 모든 웹 프로젝트에 대 한 단일 루트 소스 제어 위치를 지정할 수 있습니다. 이 단일 루트는 슈퍼 통합 루트 (도메인 이름 얻기) 라고 합니다.  
  
 소스 제어 플러그 인 API 버전 1.1에서에서 사용자 다중 프로젝트 솔루션을 소스 제어에 추가 하는 경우 사용자가 지정 하 라는 메시지가 각 웹 프로젝트에 대해 하나의 소스 제어 대상입니다.  
  
## <a name="new-capability-flags"></a>새 기능 플래그  
 `SCC_CAP_CREATESUBPROJECT`  
  
 `SCC_CAP_GETPARENTPROJECT`  
  
## <a name="new-functions"></a>새로운 함수  
 [SccCreateSubProject](../../extensibility/scccreatesubproject-function.md)  
  
 [SccGetParentProjectPath](../../extensibility/sccgetparentprojectpath-function.md)  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 제어에 솔루션을 추가 하는 경우 거의 항상 IDE 도메인 이름 얻기 폴더 만듭니다. 특히,이 작업을 수행 다음과 같은 경우:  
  
-   프로젝트에 파일 공유 웹 프로젝트입니다.  
  
-   프로젝트 및 솔루션 파일에 대 한 다양 한 드라이브 있습니다.  
  
-   프로젝트 및 솔루션 파일에 대 한 다른 공유 있습니다.  
  
-   프로젝트에에서 추가 된 별도로 (소스 제어에서 솔루션).  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 도메인 이름 얻기 폴더에 대 한 이름 확장명 없이 솔루션 이름으로 동일할 것이 좋습니다. 다음 표에서 두 가지 버전으로 동작을 요약 합니다.  
  
|기능|tSource 제어 플러그 인 API 버전 1.1|소스 제어 플러그 인 API 버전 1.2|  
|-------------|----------------------------------------------|---------------------------------------------|  
|소스 코드 제어에 솔루션 추가|SccInitialize()<br /><br /> SccGetProjPath()<br /><br /> SccGetProjPath()<br /><br /> SccOpenProject()|SccInitialize()<br /><br /> SccGetProjPath()<br /><br /> SccCreateSubProject()<br /><br /> SccCreateSubProject()<br /><br /> SccOpenProject()|  
|소스 제어에서 솔루션에 프로젝트 추가|SccGetProjPath()<br /><br /> OpenProject()|SccGetParentProjectPath()<br /><br /> SccOpenProject() **참고:** Visual Studio는 솔루션의 SUR.의 직계 자식이 이라고 가정|  
  
## <a name="examples"></a>예제  
 다음 표에서 두 가지 예를 나열합니다. 두 경우 모두는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 될 때까지 소스 제어에서 솔루션에 대 한 대상 위치에 대 한 메시지가 표시 됩니다는 *user_choice* 를 대상으로 지정 합니다. user_choice를 지정 하는 경우 소스 제어 대상에 대 한 사용자 확인 없이 솔루션과 두 개의 프로젝트가 추가 됩니다.  
  
|솔루션에 포함 되어|디스크 위치에|데이터베이스 기본 구조|  
|-----------------------|-----------------------|--------------------------------|  
|sln1.sln<br /><br /> W e b 1<br /><br /> Web2|C:\Solutions\sln1<br /><br /> C:\Inetpub\wwwroot\Web1<br /><br /> \\\server\wwwroot$\web2|$/*user_choice*/sln1<br /><br /> $/*user_choice*  /C/w e b 1<br /><br /> $/*user_choice*/Web2|  
|sln1.sln<br /><br /> W e b 1<br /><br /> Win1|C:\Solutions\sln1<br /><br /> D:\Inetpub\wwwroot\Web1<br /><br /> C:\solutions\sln1\Win1|$/*user_choice*/sln1<br /><br /> $/*user_choice*  /D/w e b 1<br /><br /> $/*user_choice*  /sln1/win1|  
  
 도메인 이름 얻기 폴더 및 하위 작업을 취소 하거나 오류로 인해 실패 여부에 관계 없이 생성 됩니다. 자동으로 취소 또는 오류 상태에서 제거 되지 않습니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 제어 플러그 인을 반환 하지 않는 경우 버전 1.1 동작을 기본값으로 `SCC_CAP_CREATESUBPROJECT` 및 `SCC_CAP_GETPARENTPROJECT` 기능 플래그입니다. 또한 사용자의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] dword: 00000001에 다음 키의 값을 설정 하 여 버전 1.1 동작으로 되돌리려면 하도록 선택할 수 있습니다.  
  
 [HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl] "DoNotCreateSolutionRootFolderInSourceControl" = dword: 00000001  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 버전 1.2의 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)