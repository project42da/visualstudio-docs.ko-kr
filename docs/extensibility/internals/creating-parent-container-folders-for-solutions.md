---
title: "솔루션에 대 한 부모 컨테이너 폴더를 만들고 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "솔루션, 부모 컨테이너를 만드는 중"
  - "소스 제어 플러그 인, 부모 컨테이너를 만드는 중"
ms.assetid: 961e68ed-2603-4479-a306-330eda2b2efa
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# 솔루션에 대 한 부모 컨테이너 폴더를 만들고
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

소스 제어 플러그 인 API에서 버전 1.2 솔루션 내에서 웹 프로젝트의 모든 단일 루트 소스 제어 대상 사용자를 지정할 수 있습니다.  이 단일 한 루트 도메인 이름 있는 수퍼 통합 루트 \(얻기\) 라고 합니다.  
  
 사용자 다중 프로젝트 솔루션을 소스 제어에 추가 하면 소스 제어 플러그 인 API에서 버전 1.1 각 웹 프로젝트에 대 한 소스 제어 대상을 지정 하 라는 되었습니다.  
  
## 새 기능 플래그  
 `SCC_CAP_CREATESUBPROJECT`  
  
 `SCC_CAP_GETPARENTPROJECT`  
  
## 새 함수  
 [SccCreateSubProject](../../extensibility/scccreatesubproject-function.md)  
  
 [SccGetParentProjectPath](../../extensibility/sccgetparentprojectpath-function.md)  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE 거의 항상 만드는 도메인 이름 얻기 폴더가 소스 제어에 솔루션을 추가 하면 됩니다.  특히 다음과 같은 경우에 제어권.  
  
-   프로젝트 파일 공유 웹 프로젝트입니다.  
  
-   프로젝트 및 솔루션 파일을 다른 드라이브에는 여러 가지가 있습니다.  
  
-   프로젝트 및 솔루션 파일에 대 한 다른 공유 됩니다.  
  
-   프로젝트와 별도로 \(소스 제어 솔루션에\)에 추가 되었습니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 확장명을 제외한 솔루션 이름으로 도메인 이름 얻기 폴더의 이름은 같을 것이 좋습니다.  다음 표에 두 가지 버전의 동작이 요약 되어 있습니다.  
  
|기능|tSource 제어 플러그 인 API 버전 1.1|소스 제어 플러그 인 API 버전 1.2|  
|--------|---------------------------------|----------------------------|  
|소스 코드 제어에 솔루션 추가|SccInitialize\(\)<br /><br /> SccGetProjPath\(\)<br /><br /> SccGetProjPath\(\)<br /><br /> SccOpenProject\(\)|SccInitialize\(\)<br /><br /> SccGetProjPath\(\)<br /><br /> SccCreateSubProject\(\)<br /><br /> SccCreateSubProject\(\)<br /><br /> SccOpenProject\(\)|  
|소스 제어 솔루션에 프로젝트 추가|SccGetProjPath\(\)<br /><br /> OpenProject\(\)|SccGetParentProjectPath\(\)<br /><br /> SccOpenProject\(\) **Note:**  Visual Studio 솔루션을 SUR.의 자식 이라고 가정|  
  
## 예제  
 다음 두 가지 예입니다.  두 경우 모두의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 묻는 때까지 소스 제어에서 솔루션에 대 한 대상 위치에 대 한의  *user\_choice* 를 대상으로 지정 됩니다.User\_choice를 지정 하면 솔루션과 두 프로젝트가 소스 제어 대상에 대 한 사용자의 확인 없이 추가 됩니다.  
  
|솔루션이 포함 되어 있습니다.|디스크 위치에서|데이터베이스의 기본 구조|  
|----------------------|--------------|-------------------|  
|sln1.sln<br /><br /> Web1<br /><br /> W e b 2|C:\\Solutions\\sln1<br /><br /> C:\\Inetpub\\wwwroot\\Web1<br /><br /> \\\\server\\wwwroot$\\web2|$\/*user\_choice*\/sln1<br /><br /> $\/*user\_choice*\/C\/Web1<br /><br /> $\/*user\_choice*\/Web2|  
|sln1.sln<br /><br /> Web1<br /><br /> Win1|C:\\Solutions\\sln1<br /><br /> D:\\Inetpub\\wwwroot\\Web1<br /><br /> C:\\solutions\\sln1\\Win1|$\/*user\_choice*\/sln1<br /><br /> $\/*user\_choice*\/D\/web1<br /><br /> $\/*user\_choice*\/sln1\/win1|  
  
 작업 취소 되거나 오류 때문에 실패 여부에 관계 없이 도메인 이름 얻기 폴더와 하위 폴더를 만듭니다.  취소 또는 오류 조건에는 자동으로 제거 되지 않습니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]소스 제어 플러그 인을 반환 하지 않는 경우 버전 1.1의 동작으로 설정 `SCC_CAP_CREATESUBPROJECT` 및 `SCC_CAP_GETPARENTPROJECT` 기능 플래그입니다.  사용자는 또한, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] dword:00000001에 다음 키 값을 설정 하 여 버전 1.1 동작으로 되돌릴 수 있습니다.  
  
 \[HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\8.0\\SourceControl\] "DoNotCreateSolutionRootFolderInSourceControl" dword:00000001 \=  
  
## 참고 항목  
 [소스 제어 플러그 인 API 버전 1.2의에서 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)