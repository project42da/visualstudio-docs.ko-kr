---
title: "RegPkg 유틸리티 | Microsoft Docs"
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
  - "regpkg, 등록 유틸리티"
  - "등록, regpkg 유틸리티"
ms.assetid: 1683ee18-59d1-4bab-a674-dd00dd960de3
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# RegPkg 유틸리티
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

> [!NOTE]
>  .Pkgdef 파일을 사용 하 여를 Visual Studio에서 패키지를 등록 하는 것이 좋습니다. 이렇게 하면 확장 배포는 VSIX 배포에 대 한 요구 사항 시스템 레지스트리를 액세스 하지 않고도 있습니다. 사용 하 여 Pkgdef 파일이 생성 되는 [CreatePkgDef 유틸리티](../../extensibility/internals/createpkgdef-utility.md)합니다. Visual Studio 패키지 배포에 대 한 자세한 내용은 참조 하십시오. [배송 Visual Studio 확장](../../extensibility/shipping-visual-studio-extensions.md)합니다.  
  
 RegPkg.exe 유틸리티와 VSPackage 등록 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 하 고 배포를 위해 준비 합니다. 이 유틸리티는 VSPackage 개발 하는 동안 백그라운드에서 사용 됩니다. 빌드하고 실험적 하이브에 VSPackage를 실행할 수 있도록 빌드 프로세스의 일부로 실행 됩니다.  
  
 RegPkg 여러 형식에서 시스템 레지스트리 스크립트를 생성할 수 있습니다. Windows Installer XML 도구 집합 파일 또는.msi 프로젝트와 같은 배포 프로젝트에서 이러한 스크립트를 통합할 수 있습니다.  
  
 RegPkg.exe은 일반적으로 \<*Visual Studio SDK 설치 경로*\> \\VisualStudioIntegration\\Tools\\Bin\\RegPkg.exe 합니다. RegPkg이이 구문은 다음과 같습니다.  
  
```  
RegPkg [/root:<root>] [/regfile:<regfile>] [/rgsfile:<rgsfile> [/rgm]] [/vrgfile:<vrgfile>] [/codebase | /assembly] [/unregister] AssemblyPath  
```  
  
 \/root:root  
 지정된 된 등록을 수행합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 루트입니다.  
  
 \/regfile:FileName  
 레지스트리를 업데이트 하는 대신.reg 파일을 만듭니다.  \/Vrgfile 또는 \/rgsfile 이나 \/wixfile와 함께 사용할 수 없습니다.  
  
 \/rgsfile:FileName  
 레지스트리를 업데이트 하는 대신.rgs 파일을 만듭니다.  \/Vrgfile 또는 \/regfile 이나 \/wixfile와 함께 사용할 수 없습니다.  
  
 \/vrgfile:FileName  
 레지스트리를 업데이트 하는 대신.vrg 파일을 만듭니다.  \/Regfile 또는 \/rgsfile 이나 \/wixfile와 함께 사용할 수 없습니다.  
  
 \/rgm  
 Rgs 파일 외에도.rgm 파일을 만듭니다.  \/Rgsfile와 결합 되어야 합니다.  
  
 \/wixfile:FileName  
 레지스트리를 업데이트 하지 않고 Windows Installer XML 도구 집합 호환 파일을 만듭니다.  \/Regfile 또는 \/rgsfile 이나 \/vrgfile와 함께 사용할 수 없습니다.  
  
 \/codebase  
 어셈블리 보다는 코드 베이스를 강제로 등록 합니다.  
  
 \/assembly  
 코드 베이스를 사용 하지 않고 어셈블리를 강제로 등록 합니다.  
  
 \/ 등록 해제  
 이 패키지를 등록 취소합니다.  사용할 수 없습니다.  
  
 \/regfile 또는 \/vrgfile 또는 \/rgsfile 또는 \/wixfile 합니다.  
  
## 참고 항목  
 [제품 릴리스](../../misc/releasing-a-visual-studio-integration-product.md)   
 [RegPkg 패키지 등록 문제 해결](../../extensibility/internals/troubleshooting-regpkg-package-registration.md)