---
title: "Windows Installer 패키지를 작성합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Vspackage.msi 파일"
  - "Vspackage msi 파일"
ms.assetid: 0ce7c21d-0d3f-47fe-a0bb-eed506e32609
caps.latest.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 20
---
# Windows Installer 패키지를 작성합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

데이터 드라이브는 Windows Installer 모델입니다. 레지스트리 항목을 쓰고 파일을 복사 프로시저 스크립트를 작성 하는 대신 예를 들어 만들 파일 및 레지스트리 데이터를 포함 하는 데이터베이스 테이블의 행과 열입니다.  
  
## 데이터베이스 항목  
 VSPackage를 설치 하려면 Windows Installer 패키지는 다음 작업을 수행할 데이터베이스 항목을 포함 해야 합니다.  
  
-   시스템의 버전을 찾을을 검색 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] VSPackage \(AppSearch, CompLocator, RegLocator, DrLocator, 및 서명을 포함 하는 Windows Installer 테이블 사용\)를 지원 합니다.  
  
-   지원 되는 버전 없는 경우 설치 취소 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 가 설치 되어 VSPackage의 다른 시스템 요구 사항 \(시작 조건 테이블 사용\)을 충족 되지 않으면 또는 합니다.  
  
-   VSPackage 및 종속 파일 \(디렉터리, 구성 요소 및 파일 테이블을 사용 하 여\) 설치 합니다.  
  
-   \(레지스트리 테이블 사용\) 하 여 레지스트리 VSPackage에 대 한 적절 한 정보를 추가 합니다.  
  
-   VSPackage에 통합 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 를 호출 하 여 **devenv.exe \/setup** \(CustomAction 테이블 사용\).  
  
 자세한 내용은 참조 [Windows Installer](http://msdn.microsoft.com/library/cc185688\(VS.85\).aspx)합니다.  
  
## 설치 프로그램 도구  
 다양 한 타사 설치 도구는 Windows Installer 패키지에 대 한 개발 환경을 제공 합니다. 두 가지 무료 도구는 다음과 같습니다.  
  
-   InstallShield Limited Edition  
  
     Visual Studio를 통해 InstallShield의 제한 된 버전을 가져올 수 있습니다 **새 프로젝트** 대화 합니다. 확장 **기타 프로젝트 형식** 선택한 다음 **설치 및 배포**합니다. InstallShield 템플릿을 선택 합니다.  
  
-   Windows Installer XML 도구 집합  
  
     도구 집합은 XML 소스 파일에서 Windows Installer 패키지를 빌드합니다. 도구 집합에는 Microsoft 오픈 소스 프로젝트입니다. 소스 코드 및 실행 파일을 다운로드할 수 있습니다 [http:\/\/sourceforge.net\/projects\/wix](http://sourceforge.net/projects/wix)합니다.  
  
 에 통합 하는 상용 제품에 대 한 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 를 사용 하 여는 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], 참조 [http:\/\/visualstudiogallery.com](http://visualstudiogallery.com/)합니다.  
  
## 참고 항목  
 [Windows Installer를 사용 하 여 Vspackage를 설치](../../extensibility/internals/installing-vspackages-with-windows-installer.md)