---
title: "테스트 소스 제어 플러그 인에 대 한 가이드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- plug-ins, source control
- source control [Visual Studio SDK], testing plug-ins
- tests, source control plug-ins
- testing, source control plug-ins
- source control plug-ins, test guide
ms.assetid: 13b74765-0b7c-418e-8cd9-5f2e8db51ae5
caps.latest.revision: "26"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0fdab6cb0b259fe169a9ebd43c92158a5ce20d4b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="test-guide-for-source-control-plug-ins"></a>테스트 소스 제어 플러그 인에 대 한 가이드
이 섹션에서는 소스 제어 플러그 인을 테스트 하기 위한 지침을 제공 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 가장 일반적인 테스트 영역은으로 더 복잡 한 영역 문제가 발생할 수 있는 광범위 한 개요를 제공 됩니다. 이 개요는 테스트 사례의 완전 한 목록을으로 다루지는지 않습니다.  
  
> [!NOTE]
>  일부 버그 수정 및 향상 된 최신 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE에 기존 소스 제어 플러그 인는 이전에 페이지가 없습니다. 이전 버전의를 사용 하는 동안 문제가 밝혀 낼 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 이 섹션에 열거 된 영역에 대 한 플러그 인 기존 소스 제어 변경 이후 적용 된 플러그 인에 이전 버전의 경우에 테스트 하는 것이 좋습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
## <a name="common-preparation"></a>일반적인 준비  
 사용 하는 컴퓨터가 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 되며 대상 소스 제어 플러그 인 설치 필요 합니다. 유사 하 게 구성 하는 두 번째 컴퓨터는 테스트 소스 제어에서에서 열기 중 일부에 대해 사용할 수 있습니다.  
  
## <a name="definition-of-terms"></a>용어 정의  
 이 테스트 예제에서는 다음과 같은 용어 정의 사용 합니다.  
  
 클라이언트 프로젝트  
 모든 프로젝트에서 사용할 수 있는 형식을 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 제어 통합을 지 원하는 (예를 들어 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)], [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)], 또는 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)]).  
  
 웹 프로젝트  
 웹 프로젝트의 네 가지가: 파일 시스템, 로컬 IIS, 원격 사이트 및 FTP 합니다.  
  
-   로컬 경로에 파일 시스템 프로젝트를 만들 수 있지만 인터넷 정보 서비스 (IIS)를 설치 하 여 UNC 경로 통해 내부적으로 액세스 하 고 클라이언트 프로젝트 매우 유사 하 게 IDE 내에서 소스 제어 아래에 있을 수 필요가 없습니다.  
  
-   로컬 IIS 프로젝트 로컬 컴퓨터를 가리키는 URL과 동일한 컴퓨터에 설치 되 고 액세스 되는 IIS를 사용 합니다.  
  
-   IIS 서비스, 원격 사이트 프로젝트를 만들 수도 있지만 소스 제어에서가 아니라 IIS 서버 컴퓨터에 아래에 배치 된 내부는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
-   원격 FTP 서버를 통해 FTP 프로젝트 액세스 하지만 소스 제어에서 사용할 수 없습니다.  
  
 인 리스트 먼 트  
 솔루션 또는 프로젝트를 소스 제어에 대 한 다른 용어입니다.  
  
 버전 저장소  
 소스 제어 플러그 인 API를 통해 액세스 되는 소스 제어 데이터베이스.  
  
## <a name="test-areas-covered-in-this-section"></a>이 섹션에서 다루는 테스트 영역  
  
-   [소스 제어에서 열기 /를 추가 하는 테스트 영역 1:](../../extensibility/internals/test-area-1-add-to-open-from-source-control.md)  
  
    -   1a 대/소문자: 소스 제어에 솔루션 추가  
  
    -   1b 대/소문자: 소스 제어에서 솔루션 열기  
  
    -   사례 1 c: 소스 제어에서 솔루션 추가  
  
-   [테스트 영역 2: 소스 제어에서 가져오기](../../extensibility/internals/test-area-2-get-from-source-control.md)  
  
-   [테스트 영역 3: 체크 아웃/체크 아웃 취소](../../extensibility/internals/test-area-3-check-out-undo-checkout.md)  
  
    -   사례 3: 체크 아웃/체크 아웃 취소  
  
    -   3a 대/소문자: 체크 아웃  
  
    -   사례 3b: 체크 아웃 연결 끊김  
  
    -   3c 사례: 쿼리 편집/쿼리 저장 (QEQS)  
  
    -   자동 체크 아웃 3d 대/소문자:  
  
    -   사례 3e: 체크 아웃 취소  
  
-   [테스트 영역 4: 체크 인](../../extensibility/internals/test-area-4-check-in.md)  
  
    -   4a 대/소문자: 수정 항목  
  
    -   4b 대/소문자: 파일 추가  
  
    -   4c 대/소문자: 프로젝트 추가  
  
-   [테스트 영역 5: 소스 제어 변경](../../extensibility/internals/test-area-5-change-source-control.md)  
  
    -   5a 대/소문자: 바인딩  
  
    -   5b 대/소문자: 바인딩 해제  
  
    -   5c 대/소문자: 다시 바인딩  
  
-   [테스트 영역 6: 삭제](../../extensibility/internals/test-area-6-delete.md)  
  
-   [테스트 영역 7: 공유](../../extensibility/internals/test-area-7-share.md)  
  
-   [테스트 영역 8: 플러그 인 전환](../../extensibility/internals/test-area-8-plug-in-switching.md)  
  
    -   8a 대/소문자: 자동 변경  
  
    -   8b 대/소문자: 솔루션을 기반으로 변경  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인](../../extensibility/source-control-plug-ins.md)