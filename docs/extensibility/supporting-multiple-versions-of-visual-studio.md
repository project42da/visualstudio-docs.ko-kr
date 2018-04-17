---
title: 여러 버전의 Visual Studio 지 원하는 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, supporting multiple versions
- VSPackages, side-by-side compatibility
ms.assetid: 0047aa90-1ed4-40d3-8772-622b2719a4b1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 317ec1f214d18989c3b2c5c27fe9df9309239631
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="supporting-multiple-versions-of-visual-studio"></a>여러 버전의 Visual Studio 지원
용어 *-나란히* 설치 하 고 동일한 컴퓨터에 있는 제품의 여러 버전을 유지 관리할 수 있는 것을 의미 합니다. 즉, Vspackage에 대 한 사용자는 동일한 컴퓨터에 설치 된 여러 Visual Studio 버전을 가질 수 있습니다. 그러나 단일 버전의 Visual Studio에 로드 하 여 Vspackage의 병렬-버전을 사용할 수 없습니다.  
  
 병렬 버전의 Visual Studio에 로드 될 수 VSPackage를 수행 하기 전에 다음 사항을 고려 합니다.  
  
-   따라 해 보려면 side-by-side-구현 전략을 결정 해야 합니다.  
  
     자세한 내용은 참조 [공유 간에 선택 및 버전 관리 된 Vspackage](../extensibility/choosing-between-shared-and-versioned-vspackages.md)합니다.  
  
-   사용자 솔루션 및 프로젝트 정의 파일 형식에 구현 전략에 맞아야 합니다.  
  
     자세한 내용은 참조 [사용자 지정 프로젝트 업그레이드](../extensibility/internals/upgrading-projects.md#upgrading-custom-projects) 및 [-병렬 배포를 위한 파일 이름 확장명 등록](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)합니다.  
  
-   설치 관리자 버전 구성 요소 및 모든 버전에서 공유 구성 요소가 올바르게 설치 되 고 등록 되도록 구현 전략을 처리 해야 합니다.  
  
     자세한 내용은 참조 [Windows Installer와 Vspackage 설치](../extensibility/internals/installing-vspackages-with-windows-installer.md) 그리고 [구성 요소 관리](../extensibility/internals/component-management.md)합니다.  
  
    > [!NOTE]
    >  해당 버전의 설치도 Visual Studio의 버전을 설치는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]합니다. 예를 들어 버전 4.0 및 4.5의 설치도 동일한 컴퓨터에 Visual Studio 2010 및 Visual Studio 2012 설치는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]각각.  
  
## <a name="in-this-section"></a>섹션 내용  
 [공유 및 버전 관리 VSPackage 중에서 선택](../extensibility/choosing-between-shared-and-versioned-vspackages.md)  
 VSPackage에서 side-by-side-문제를 해결 하는 방법에 설명 합니다.  
  
 [병렬 배포를 위해 파일 이름 확장명 등록](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)  
 VSPackage가-병렬 시나리오에서 파일 연결을 등록할 수는 방법에 대해 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [Windows Installer를 사용하여 VSPackage 설치](../extensibility/internals/installing-vspackages-with-windows-installer.md)  
