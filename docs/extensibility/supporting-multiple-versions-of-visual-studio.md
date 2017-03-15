---
title: "여러 버전의 Visual Studio 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "여러 버전을 지 원하는 visual Studio"
  - "Vspackage를 side-by-side-호환성"
ms.assetid: 0047aa90-1ed4-40d3-8772-622b2719a4b1
caps.latest.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 20
---
# 여러 버전의 Visual Studio 지원
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

용어 *side\-by\-side\-* 설치 되 고 동일한 컴퓨터에 있는 제품의 여러 버전을 유지 관리할 수 있습니다. Vspackage에 대 한 즉, 사용자는 동일한 컴퓨터에 설치 하는 몇 가지 Visual Studio 버전 있을 수 있습니다. 그러나 단일 버전의 Visual Studio에 로드 하 여 Vspackage의 side\-by\-side\-버전을 가질 수 없습니다.  
  
 Side\-by\-side\-버전의 Visual Studio에 로드할 수 VSPackage를 수행 하기 전에 다음 사항을 고려 합니다.  
  
-   수행 하려는\-나란히 구현 전략을 결정 해야 합니다.  
  
     자세한 내용은 [Vspackage를 공유 하 고 버전 중에서 선택](../extensibility/choosing-between-shared-and-versioned-vspackages.md)을 참조하십시오.  
  
-   사용자의 솔루션 및 프로젝트 파일 형식 구현 전략에 맞아야 합니다.  
  
     자세한 내용은 [사용자 지정 프로젝트 업그레이드](../misc/upgrading-custom-projects.md) 및 [병렬 배포에 대 한 파일 이름 확장명을 등록 하는 중입니다.](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)를 참조하세요.  
  
-   설치 관리자는 버전이 지정 된 구성 요소 및 모든 버전에서 공유 하는 구성 요소가 올바르게 설치 되어 등록 되도록 구현 전략을 처리 해야 합니다.  
  
     자세한 내용은 참조 [Windows Installer를 사용 하 여 Vspackage를 설치](../extensibility/internals/installing-vspackages-with-windows-installer.md) 도 [구성 요소 관리](../extensibility/internals/component-management.md)합니다.  
  
    > [!NOTE]
    >  해당 버전의 설치 버전의 Visual Studio를 설치 하는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]합니다. 예를 들어 버전 4.0 및 4.5의 설치도 동일한 컴퓨터에 Visual Studio 2010 및 Visual Studio 2012 설치는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], 각각.  
  
## 단원 내용  
 [Vspackage를 공유 하 고 버전 중에서 선택](../extensibility/choosing-between-shared-and-versioned-vspackages.md)  
 VSPackage에서 side\-by\-side\-문제를 해결 하는 방법에 설명 합니다.  
  
 [병렬 배포에 대 한 파일 이름 확장명을 등록 하는 중입니다.](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)  
 VSPackage가\-병렬 시나리오에서 파일 연결을 등록할 수는 방법에 대해 설명 합니다.  
  
## 관련 단원  
 [VSPackage 설치](../misc/installing-vspackages.md)  
 동시에 여러 버전의 Visual Studio를 실행 하는 사용자를 지 원하는 방법과 빌드하고 Vspackage를 설치 하는 방법에 설명 합니다.