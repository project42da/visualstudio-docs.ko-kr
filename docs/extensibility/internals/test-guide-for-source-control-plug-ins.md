---
title: "소스 제어 플러그 인에 대 한 테스트 가이드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "플러그 인, 소스 제어"
  - "플러그 인을 테스트 소스 제어 [Visual Studio SDK]"
  - "테스트를 소스 제어 플러그 인"
  - "테스트, 소스 제어 플러그 인"
  - "소스 제어 플러그 인, 테스트 가이드"
ms.assetid: 13b74765-0b7c-418e-8cd9-5f2e8db51ae5
caps.latest.revision: 26
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 26
---
# 소스 제어 플러그 인에 대 한 테스트 가이드
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 섹션에서는 테스트를 소스 제어 플러그 인에 대 한 가이드를 제공 합니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  가장 일반적인 테스트 영역으로 일부 문제를 더 복잡 한 영역은 광범위 한 개요를 제공 합니다.  이 개요는 완결 테스트 사례를 제공 하지 않습니다.  
  
> [!NOTE]
>  몇 가지 버그 수정 사항 및 향상 된 최신 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE 기존 소스 제어의 이전 버전을 사용 하는 동안 이전에 발생 않은 플러그 인에 문제가 발견 될 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  플러그 인을 이후에 이전 버전의 변경 된 내용이 경우에 기존 소스 제어 플러그 인에 대해이 섹션에서 열거 된 영역을 테스트 하는 것이 좋습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## 일반적인 준비  
 컴퓨터와 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 및 대상 소스 제어 플러그 인 설치에 필요 합니다.  일부 테스트를 소스 제어에서 열기에 대 한 유사 하 게 구성 된 다른 컴퓨터를 사용할 수 있습니다.  
  
## 용어 정의  
 이 테스트 설명서를 다음과 같은 용어 정의 사용 합니다.  
  
 클라이언트 프로젝트  
 모든 프로젝트 형식에 사용할 수 있는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 제어 통합을 지 원하는 \(예를 들어, [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)], [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)], 또는 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)]\).  
  
 웹 프로젝트  
 웹 프로젝트의 네 가지: 파일 시스템, 로컬 IIS, 원격 사이트 및 FTP입니다.  
  
-   파일 시스템 프로젝트는 로컬 경로에 만들어집니다 있지만 내부적으로 UNC 경로 통해 액세스 하는 하 고 클라이언트 프로젝트와 마찬가지로, IDE 내에서 소스 제어에 배치할 수 있습니다 설치 되어 인터넷 정보 서비스 \(IIS\) 필요 하지 않습니다.  
  
-   로컬 IIS 프로젝트에 액세스할 때와 동일한 컴퓨터에 설치 된 IIS 로컬 컴퓨터로 가리키는 URL와 함께 작동 합니다.  
  
-   원격 사이트 프로젝트는 IIS 서비스 아래에서 만들 수도 있지만 소스 제어에서 하 고 IIS 서버 컴퓨터에 배치 됩니다 내에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
-   원격 FTP 서버를 통해 FTP 프로젝트 액세스 되지만 소스 제어에 배치할 수 없습니다.  
  
 인 리스트 먼 트  
 솔루션 또는 프로젝트를 소스 제어에 대 한 또 다른 용어입니다.  
  
 버전 저장소  
 소스 제어 플러그 인 API를 통해 액세스 되는 소스 제어 데이터베이스입니다.  
  
## 이 섹션에서 다루는 테스트 영역  
  
-   [소스 제어에서 열기 \/를 추가 하는 테스트 영역 1:](../../extensibility/internals/test-area-1-add-to-open-from-source-control.md)  
  
    -   이 경우 1a: 소스 제어에 솔루션 추가  
  
    -   이 경우 1b: 소스 제어에서 솔루션 열기  
  
    -   1 C 사례: 소스 제어에서 솔루션을 추가 합니다.  
  
-   [소스 제어에서 가져올 테스트 영역 2:](../../extensibility/internals/test-area-2-get-from-source-control.md)  
  
-   [테스트 영역 3: 체크 아웃\/체크 아웃 취소](../../extensibility/internals/test-area-3-check-out-undo-checkout.md)  
  
    -   사례 3: 체크 \/ 체크 아웃 명령 취소  
  
    -   이 경우 3a: 체크 아웃  
  
    -   3B 케이스: 연결이 체크 아웃  
  
    -   3 C 사례: 쿼리 편집\/쿼리 저장 \(QEQS\)  
  
    -   3D 사례: 자동 체크 아웃  
  
    -   3E 케이스: 체크 아웃 취소  
  
-   [테스트 영역 4: 체크 인](../../extensibility/internals/test-area-4-check-in.md)  
  
    -   이 경우 4a: 항목 수정  
  
    -   이 경우 4b: 파일 추가  
  
    -   4 C 사례: 프로젝트 추가  
  
-   [소스 제어를 변경 하는 테스트 영역 5:](../../extensibility/internals/test-area-5-change-source-control.md)  
  
    -   5A 경우: 바인딩  
  
    -   5B 케이스: 바인딩 해제  
  
    -   5 C 사례: 다시 바인딩  
  
-   [테스트 영역 6: 삭제](../../extensibility/internals/test-area-6-delete.md)  
  
-   [테스트 영역 7: 공유](../../extensibility/internals/test-area-7-share.md)  
  
-   [플러그 인 전환을 테스트 영역 8:](../../extensibility/internals/test-area-8-plug-in-switching.md)  
  
    -   8A 사례: 자동 변경  
  
    -   이 경우 8b: 솔루션 기반으로 변경  
  
## 참고 항목  
 [소스 제어 플러그 인](../../extensibility/source-control-plug-ins.md)