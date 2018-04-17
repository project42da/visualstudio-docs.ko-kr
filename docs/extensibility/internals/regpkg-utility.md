---
title: RegPkg 유틸리티 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- regpkg, registration utility
- registration, regpkg utility
ms.assetid: 1683ee18-59d1-4bab-a674-dd00dd960de3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5d677aaf155e533c27a775f3995b53dd59b65385
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="regpkg-utility"></a>RegPkg 유틸리티
> [!NOTE]
>  .Pkgdef 파일을 사용 하 여를 Visual Studio에서 패키지를 등록 하는 것이 좋습니다. 그러면 VSIX 배포에 대 한 요구 사항인 시스템 레지스트리에 액세스 하지 않고도 확장 배포. 사용 하 여 Pkgdef 파일을 만듭니다는 [CreatePkgDef 유틸리티](../../extensibility/internals/createpkgdef-utility.md)합니다. Visual Studio 패키지 배포에 대 한 자세한 내용은 참조 하십시오. [Visual Studio 확장명 전달](../../extensibility/shipping-visual-studio-extensions.md)합니다.  
  
 RegPkg.exe 유틸리티가와 VSPackage 등록 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 하 고 배포를 위해 준비 합니다. 이 유틸리티는 원리를 자세히 파악할수록 VSPackage 개발 하는 동안 사용 됩니다. 빌드하고의 실험 하이브에서 VSPackage를 실행할 수 있도록 빌드 프로세스의 일부로 실행 합니다.  
  
 RegPkg 몇 가지 형식으로 시스템 레지스트리 스크립트를 생성할 수 있습니다. .Msi 프로젝트 또는 Windows Installer XML 도구 집합 파일과 같은 배포 프로젝트에서 이러한 스크립트를 통합할 수 있습니다.  
  
 RegPkg.exe은 일반적으로 \< *Visual Studio SDK 설치 경로*> \VisualStudioIntegration\Tools\Bin\RegPkg.exe 합니다. RegPkg이이 구문은 다음과 같습니다.  
  
```  
RegPkg [/root:<root>] [/regfile:<regfile>] [/rgsfile:<rgsfile> [/rgm]] [/vrgfile:<vrgfile>] [/codebase | /assembly] [/unregister] AssemblyPath  
```  
  
 /root:root  
 지정 된 등록을 수행합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 루트입니다.  
  
 /regfile:FileName  
 레지스트리를 업데이트 하는 대신.reg 파일을 만듭니다.  /Vrgfile 또는 /rgsfile 이나 /wixfile와 함께 사용할 수 없습니다.  
  
 /rgsfile:FileName  
 레지스트리를 업데이트 하는 대신.rgs 파일을 만듭니다.  /Vrgfile 또는 /regfile 이나 /wixfile와 함께 사용할 수 없습니다.  
  
 /vrgfile:FileName  
 레지스트리를 업데이트 하는 대신.vrg 파일을 만듭니다.  /Regfile 또는 /rgsfile 이나 /wixfile와 함께 사용할 수 없습니다.  
  
 /rgm  
 Rgs 파일 외에도.rgm 파일을 만듭니다.  /Rgsfile와 결합 되어야 합니다.  
  
 /wixfile:FileName  
 레지스트리를 업데이트 하는 대신 Windows Installer XML 도구 집합 호환 파일을 만듭니다.  /Regfile 또는 /rgsfile 이나 /vrgfile와 함께 사용할 수 없습니다.  
  
 /codebase  
 어셈블리 보다는 코드 베이스에 강제로 등록 합니다.  
  
 /assembly  
 코드 베이스를 사용 하지 않고 어셈블리에 강제로 등록 합니다.  
  
 /unregister  
 이 패키지를 등록 취소합니다.  사용할 수 없습니다.  
  
 /regfile 또는 /vrgfile /rgsfile 또는 /wixfile 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [VSPackage](../../extensibility/internals/vspackages.md)  
 [RegPkg 패키지 등록 문제 해결](../../extensibility/internals/troubleshooting-regpkg-package-registration.md)