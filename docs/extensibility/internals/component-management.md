---
title: 구성 요소 관리 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- installation [Visual Studio SDK], components
- installation [Visual Studio SDK], file management
ms.assetid: 029bffa2-6841-4caa-a41a-442467e1aedc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2798d820249f0a1c4310569d22d8510710ca13ee
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="component-management"></a>구성 요소 관리
Windows Installer에서 작업의 단위는 Windows Installer 구성 요소가 (WICs 또는 정당한 구성 요소 라고도 함) 라고 합니다. GUID는 설치 및 Windows Installer를 사용 하 여 설치를 사용한 참조의 기본 단위를 각 WIC를 식별 합니다.  
  
 VSPackage installer를 만드는 몇 가지 제품을 사용 하 여 있지만이 설명에서는 Windows Installer (.msi) 파일의 사용을 가정 합니다. 설치 관리자를 만들 때 올바른 참조 횟수를 항상 수행 되도록 파일 배포 올바르게 관리 해야 합니다. 따라서 제품의 다른 버전 됩니다 하지 또는 서로 혼합 하 여 설치를 중단을 방해할 시나리오를 제거 합니다.  
  
 Windows installer에서 구성 요소 수준에서 발생 참조 횟수 계산 합니다. 리소스를 신중 하 게 구성 해야-파일, 레지스트리 항목 및 등-구성 요소에 있습니다. 다른 수준의 조직-모듈, 기능 및 제품 같은-다양 한 시나리오에서 데 사용할 수 있는 합니다. 자세한 내용은 참조 [Windows Installer 기본 사항](../../extensibility/internals/windows-installer-basics.md)합니다.  
  
## <a name="guidelines-of-authoring-setup-for-side-by-side-installation"></a>제작-나란히 설치에 대 한 설치 지침  
  
-   작성자 파일 및 레지스트리 키를 직접 구성 요소로 버전 간에 공유 되는 합니다.  
  
     그러면 다음 버전에서이 쉽게 사용할 수 있습니다. 예를 들어 전역으로 등록 된 형식 라이브러리 파일 확장명, HKEY_CLASSES_ROOT, 및 기타 등등에 등록 된 다른 항목을 사용 합니다.  
  
-   별도 병합 모듈에 공유 구성 요소를 그룹화 합니다.  
  
     이렇게 하면 작성자-함께 일경에 올바로 있습니다.  
  
-   여러 버전에서 동일한 Windows Installer 구성 요소를 사용 하 여 공유 파일 및 레지스트리 키를 설치 합니다.  
  
     다른 구성 요소를 사용 하는 경우 한 버전 관리 된 VSPackage를 제거 하지만 다른 VSPackage 여전히 설치 하는 경우이 파일과 레지스트리 항목이 제거 됩니다.  
  
-   동일한 구성 요소의 버전 관리 및 공유 항목을 혼합 하지 마십시오.  
  
     이렇게 하면 전역 위치 및 격리 된 위치에 버전이 지정 된 항목 공유 항목을 설치 하는 불가능 합니다.  
  
-   버전이 지정 파일을 가리키는 공유 레지스트리 키를 갖지 않습니다.  
  
     이렇게 하면 다른 버전 관리 된 VSPackage를 설치할 때 공유 키 덮어쓸 수 있습니다. 두 번째 버전을 제거한 후 키가 가리키고 파일이 사라집니다.  
  
## <a name="see-also"></a>참고 항목  
 [공유 및 버전 지정 Vspackage 중에서 선택](../../extensibility/choosing-between-shared-and-versioned-vspackages.md)   
 [VSPackage 설치 시나리오](../../extensibility/internals/vspackage-setup-scenarios.md)