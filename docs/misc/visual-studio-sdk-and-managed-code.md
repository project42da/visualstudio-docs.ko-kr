---
title: "Visual Studio SDK 및 관리 코드 | Microsoft Docs"
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
  - "VSIP, 관리 코드 정보"
ms.assetid: 16b3d88e-b5d8-49a5-a5d7-07cbb0b7e4fc
caps.latest.revision: 20
caps.handback.revision: 20
manager: "douge"
---
# Visual Studio SDK 및 관리 코드
*관리 되는 코드* 와 같은 공용 언어 런타임 \(CLR\)을 대상으로 하는 모든 언어로 작성 된 코드는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)], 또는 [!INCLUDE[vcprvc](../debugger/includes/vcprvc_md.md)].  작성 된 언어에 관계 없이 모든 관리 코드 Microsoft 중간 언어 \(MSIL로\) 대신 기본 코드가 컴파일됩니다.  
  
## 관리 되는 Vspackages에 대 한 환경 지원  
 만든 Vspackage를 지원 하거나 같은 관리 되는 언어와 프로젝트 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]의 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 다음을 제공 합니다.  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 관리 되는 코드로 작성 된 VSPackages 관리 되지 않는 \(COM\) 상호 운용이 가능 하 게 하는 interop 어셈블리 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\)입니다.  자세한 내용은 [Visual Studio Interop 어셈블리를 사용 하 여](../extensibility/internals/using-visual-studio-interop-assemblies.md)를 참조하십시오.  
  
-   작업에 대 한 더 높은 수준의 추상화를 제공 하는 패키지 관리 프레임 워크 \(MPF\) 클래스는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE.  이 클래스는 몇 가지 가장 자주 사용 되는 인터페이스 및 형식에 캡슐화는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] interop 어셈블리입니다.  크게 VSPackage 또는 프로젝트의 기본적인 기능을 위해 수행 해야 할 작업의 양을 줄일 수 있습니다.  자세한 내용은 [관리되는 패키지 프레임워크 클래스](../misc/managed-package-framework-classes.md)를 참조하십시오.  
  
-   관리 되는 코드로 작성 하는 기본적인 VSPackage 샘플의 집합입니다.  관리 되는 샘플의 기본 편집기, 도구 창, 개체가 extender 및 기타 구성 요소를 설명 하는 간단 하 고 완벽 하 게 작동 VSPackage 예를 빌드합니다.  자세한 내용은 [VSSDK 샘플](../misc/vssdk-samples.md)를 참조하십시오.  
  
## 참고 항목  
 [관리되는 VSPackage](../misc/managed-vspackages.md)   
 [Visual Studio Interop 어셈블리를 사용 하 여](../extensibility/internals/using-visual-studio-interop-assemblies.md)   
 [관리되는 패키지 프레임워크 클래스](../misc/managed-package-framework-classes.md)