---
title: "구성 요소 관리 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "구성 요소 설치 [Visual Studio SDK]"
  - "설치 [Visual Studio SDK] 파일 관리"
ms.assetid: 029bffa2-6841-4caa-a41a-442467e1aedc
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 구성 요소 관리
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Windows Installer의 작업 단위를 WICs 또는 단지 구성 요소 라고도 하는 Windows Installer 구성 요소로 라고 합니다.  GUID를 기본 단위로 설치 및 참조 횟수 Windows Installer를 사용 하는 설치의 경우 각 WIC를 식별 합니다.  
  
 VSPackage 설치 관리자를 만들려면 몇 가지 제품을 사용할 수 있지만이 토론 Windows Installer \(.msi\) 파일의 사용을 가정 합니다.  항상 올바른 참조 횟수가 발생 하는 설치 관리자를 만들 때 파일 배포를 제대로 관리 해야 합니다.  따라서 서로 다른 버전의 제품을 방해 또는 서로 혼합 된 설치를 중단 되거나 되지 시나리오를 제거 합니다.  
  
 Windows Installer의 참조 횟수는 구성 요소 수준에서 발생합니다.  리소스를 신중 하 게 구성 해야\-파일, 레지스트리 항목, 등\-구성 요소에 있습니다.  다른 수준의 조직\-모듈, 기능 및 제품 등\-다양 한 시나리오에서 도움이 됩니다.  자세한 내용은 [Windows Installer 기본 사항](../../extensibility/internals/windows-installer-basics.md)를 참조하십시오.  
  
## 병렬 설치를 위해 설치 프로그램 제작 지침  
  
-   작성자 파일과 구성 요소로 버전에서 공유 하는 레지스트리 키입니다.  
  
     이렇게 하면 쉽게 다음 버전에서이 사용할 수 있습니다.  예를 들어, 전역으로 등록 된 형식 라이브러리 파일 확장명을 HKEY\_CLASSES\_ROOT, 등에서 등록 항목입니다.  
  
-   공유 구성 요소를 별개의 병합 모듈로 그룹화 합니다.  
  
     이렇게 하면 작성자를\-\-앞으로 나란히에 사용할 수 있습니다.  
  
-   버전 간에 동일한 Windows Installer 구성 요소를 사용 하 여 공유 파일 및 레지스트리 키를 설치 합니다.  
  
     다른 구성 요소를 사용 하는 경우 파일 및 레지스트리 항목 버전이 있는 VSPackage 하나를 제거 하는 또 다른 VSPackage 여전히 설치 되어 때 제거 됩니다.  
  
-   버전이 관리 되 고 공유 항목에 동일한 구성 요소를 섞지 마십시오.  
  
     이렇게 전역 위치 및 버전이 있는 항목 격리 된 위치에 공유 항목을 설치할 수 있습니다.  
  
-   버전의 파일을 가리키는 공유 레지스트리 키가 없는.  
  
     이렇게 하면 다른 버전의 Vspackage를 설치할 때 공유 키 덮어쓰게 됩니다.  키를 가리키는 파일의 두 번째 버전을 제거한 후에 없어집니다.  
  
## 참고 항목  
 [Vspackage를 공유 하 고 버전 중에서 선택](../../extensibility/choosing-between-shared-and-versioned-vspackages.md)   
 [VSPackage 설치 시나리오](../../extensibility/internals/vspackage-setup-scenarios.md)