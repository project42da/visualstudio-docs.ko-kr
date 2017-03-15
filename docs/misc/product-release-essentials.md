---
title: "제품 릴리스 필수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "배포, 필수"
  - "설치[Visual Studio SDK], 필수"
ms.assetid: 28370bc8-f3a7-4c5e-9b35-8331cda14ff4
caps.latest.revision: 12
caps.handback.revision: 12
manager: "douge"
---
# 제품 릴리스 필수
재미있고 강력한 설치 환경은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합 제품에 대해 사용자의 마음에 지속적인 인상을 형성합니다. 불쾌한 설치 환경 역시 지속적인 인상을 형성하므로 설치 개발의 모범 사례를 따르고 테스트하는 것은 투자할 가치가 있습니다.  
  
## Windows Installer 설치 패키지 개발  
 Windows Installer는 Windows 및 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합 제품에 대한 권장 설치 및 구성 서비스입니다.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합 제품 설치에 대한 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 설명서는 Windows Installer 개념을 기반으로 하지만 Windows Installer 자체를 다루지는 않습니다. Windows Installer 설명서의 관련 섹션에 대한 링크는 아래 표를 참조하세요.  
  
 설치 컨텍스트에서 *구성 요소*는 Windows Installer 구성 요소를 참조합니다. 구성 요소는 파일 및 레지스트리 항목 등의 리소스를 포함하며 하나의 단위로 설치하고 제거합니다.  
  
|작업|詳細については、次のトピックを参照してください。|  
|--------|------------------------------|  
|Windows Installer에 대해 알아봅니다.|[Windows Installer](http://msdn.microsoft.com/library/aa372866.aspx)|  
|VSPackage의 시스템 요구 사항을 확인합니다.|-   [시스템 요구 사항 검색](../extensibility/internals/detecting-system-requirements.md)|  
|설치 패키지에서 VSPackage를 등록하는 방법을 알아봅니다.|-   [VSPackage 등록](../extensibility/internals/vspackage-registration.md)<br />-   [설치 후 실행 해야 하는 명령](../extensibility/internals/commands-that-must-be-run-after-installation.md)|  
|샘플 설치 패키지를 참조하세요.|-   IronPython 통합 설치 샘플|  
  
## Side\-by\-Side 제품 지원  
 Side\-by\-Side\(경우에 따라 *SxS*로 축소\)는 동일한 제품의 여러 버전을 설치하고 동시에 실행하기도 하는 기능을 나타냅니다.[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합 제품의 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 자체에서 Side\-by\-Side 실행을 지원한다는 사실도 나타냅니다.  
  
|작업|詳細については、次のトピックを参照してください。|  
|--------|------------------------------|  
|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합 제품에서 여러 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 지원에 대해 알아봅니다.|-   [Vspackage를 공유 하 고 버전 중에서 선택](../extensibility/choosing-between-shared-and-versioned-vspackages.md)<br />-   [구성 요소 관리](../extensibility/internals/component-management.md)|  
|여러 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합 제품 지원에 대해 알아봅니다.|-   [Vspackage를 공유 하 고 버전 중에서 선택](../extensibility/choosing-between-shared-and-versioned-vspackages.md)<br />-   [병렬 배포에 대 한 파일 이름 확장명을 등록 하는 중입니다.](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)<br />-   [시스템 요구 사항 검색](../extensibility/internals/detecting-system-requirements.md)<br />-   [설치 후 실행 해야 하는 명령](../extensibility/internals/commands-that-must-be-run-after-installation.md)|  
  
## Visual Studio 통합 제품 테스트  
 VSIT\([!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합 테스트\) 도구 모음은 VSPackage가 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]로 올바르게 통합되는지 확인하는 일련의 테스트입니다. VSIT는 VSPackage의 기능을 테스트하지 않지만 VSPackage가 다른 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 기능에 부정적인 영향을 주지 않는지 확인하는 데 도움이 됩니다. 자세한 내용은 [Visual Studio 통합 테스트](http://msdn.microsoft.com/ko-kr/8d741735-7d93-46c2-ab93-01da7a0e016d)를 참조하세요.