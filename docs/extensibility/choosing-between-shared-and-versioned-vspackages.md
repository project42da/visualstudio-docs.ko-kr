---
title: 공유 및 버전 지정 Vspackage 중에서 선택 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- SxS
- side-by-side installation
- installation [Visual Studio SDK], side-by-side
ms.assetid: e3128ac3-2e92-48e9-87ab-3b6c9d80e8c9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ce7f58d664c6a186146272af16324be2fee90983
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="choosing-between-shared-and-versioned-vspackages"></a>공유 및 버전 지정 Vspackage 중에서 선택
다른 버전의 Visual Studio는 동일한 컴퓨터에 사용할 수 있습니다. Vspackage의 혼합을 지원할 수 있는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 버전입니다.  
  
 -설치 Vspackage의 두 가지 전략, 공유 전략 또는 버전이 있는 전략 중 하나를 통해 사용할 수 있습니다. 여러 버전의 현재 상태를 수용 하는 둘 다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 및 버전의 관련는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]합니다.  
  
 공유 전략의 여러 버전에서 사용 하기 위해 하나의 VSPackage 등록 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 버전 관리 전략에 여러 VSPackage Dll이 설치의 각 버전에 대 한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 지 원하는 합니다.  
  
## <a name="shared-vspackages"></a>공유 Vspackage  
 공유 VSPackage를 사용 하는 동일한 VSPackage를 사용 하 여 여러 버전의 경우 적절 한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 공유 VSPackage를 구현 하려면 다음 단계를 수행 해야 합니다.  
  
-   VSPackage의 여러 버전을 호환 되 게 만들기 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 이렇게 두 가지 방법으로 되므로 사용할 수 있습니다.  
  
    -   가장 오래 된 버전의 기능을 사용 하 여 VSPackage 제한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 지 원하는 합니다.  
  
    -   버전을 적용 하기 위해 VSPackage를 프로그래밍 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 실행 되는에 있습니다. 그런 다음 새로운 서비스에 대 한 쿼리가 실패 하는 경우 VSPackage 제공할 수의 이전 버전에서 지원 되는 다른 서비스 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
-   적절 하 게 VSPackage를 등록 합니다. 자세한 내용은 참조 [VSPackage 등록](../extensibility/internals/vspackage-registration.md) 및 [관리 되는 VSPackage 등록](http://msdn.microsoft.com/en-us/f69e0ea3-6a92-4639-8ca9-4c9c210e58a1)합니다.  
  
-   파일 확장명을 적절 하 게 등록 합니다. 자세한 내용은 참조 [-병렬 배포를 위한 파일 이름 확장명 등록](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)합니다.  
  
-   적절 한 버전의 VSPackage를 배포 하는 설치 관리자를 만들 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 자세한 내용은 참조 [Windows Installer와 Vspackage 설치](../extensibility/internals/installing-vspackages-with-windows-installer.md) 및 [구성 요소 관리](../extensibility/internals/component-management.md)합니다.  
  
-   등록 충돌 문제를 해결 합니다. 자세한 내용은 참조 [VSPackage 등록](../extensibility/internals/vspackage-registration.md)합니다.  
  
-   파일 공유 및 버전 관리 된 여러 버전의 안전 설치 및 제거를 허용 하기 위해 참조 가산을 준수를 확인 합니다. 자세한 내용은 참조 [구성 요소 관리](../extensibility/internals/component-management.md)합니다.  
  
## <a name="versioned-vspackages"></a>Vspackage 버전  
 각 버전에 대 한 하나의 VSPackage를 만들면 버전 VSPackage 전략 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 지 원하는 합니다. 이 방법을 적절 한 이후 버전의에서 제공 하는 서비스를 활용 하려는 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]다른 영향을 주지 않고 각 VSPackage 수 발전 때문에 있습니다. 그럼에도 불구 하 고 단일 코드 베이스에서 또는 여러 독립적인 코드 베이스에서 여러 이진 파일을 만드는 버전 관리 전략에는 공유 전략 보다 더 많은 초기 개발을 해야 할 수 있습니다. 또한, 추가 설정 작업이 필요할 수도 각 버전에 대 한 별도 설치 또는 버전을 검색 하는 단일 설치를 만들어야 하기 때문에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설치 되어 있고 VSPackage를 지원 합니다.  
  
## <a name="binary-compatibility"></a>이진 호환성  
 일반적으로 이진 호환성 이전 버전의 Visual Studio의 이후 버전에서 실행 하려면 Visual Studio를 사용 하 여 개발 하는 네이티브 코드로 Vspackage를 수 있습니다. 그러나 중요 한 세 가지 예외가 있습니다.  
  
-   VSPackage는 특정 버전의 공용 언어 런타임 사용 경우 어떤 버전의에서 결정 해야 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 실행 되 고 있습니다.  
  
-   VSPackage는 다른 VSPackage 또는 다른 제품의 특정 기능에 대 한 종속성이 있을 수 있습니다. 따라서 VSPackage만 있는 종속성을 충족 하는 것을 실행할 수 있습니다.  
  
-   VSPackage의 보안 수정 영향을 받을 수는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 서비스 팩 또는 최신 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 이러한 경우에는 VSPackage의 이전 버전을 사용 하 여 개발 된 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 버전에서 실행 되지 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 보안 수정이 적용 된 후입니다. 그러나 이후 버전으로 패키지를 다시 작성할 수 있으며 또한 이전 버전에서에서 실행할 수 있습니다.  
  
 관리 되는 Vspackage의 버전을 사용 하 여 빌드해야 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 및 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 의 대상 버전이 일치 하는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
 VSPackage 이진에 대 한 이진 호환성에 대 한 계획, 외에 사항과 고려해 야 솔루션 프로젝트 파일 형식입니다. 여러 버전의 또는 하나의 버전에서 실행할 수 있는지 여부를 결정 해야 새 프로젝트 형식을 VSPackage를 만드는 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 자세한 내용은 참조 [사용자 지정 프로젝트 업그레이드](../extensibility/internals/upgrading-projects.md#upgrading-custom-projects)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Installer를 사용 하 여 Vspackage 설치](../extensibility/internals/installing-vspackages-with-windows-installer.md)   
 [구성 요소 관리](../extensibility/internals/component-management.md)