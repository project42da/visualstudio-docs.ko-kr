---
title: "관리되는 패키지 프레임워크 클래스 | Microsoft Docs"
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
  - "관리되는 패키지 프레임워크, 도우미 클래스"
  - "관리되는 패키지 도우미 클래스"
  - "Visual Studio SDK, 관리되는 패키지 도우미 클래스"
  - "클래스[Visual Studio SDK], 관리되는 패키지 프레임워크"
ms.assetid: 15aedcc3-c79a-460b-b620-43223f1ae81e
caps.latest.revision: 24
caps.handback.revision: 24
manager: "douge"
---
# 관리되는 패키지 프레임워크 클래스
MPF\(관리되는 패키지 프레임워크\) 클래스를 사용하여 관리 코드를 사용하는 Vspackage를 만들 수 있습니다. 이 클래스는 많은 VSPackage 인터페이스에 대한 기본 구현을 제공합니다. MPF는 구현 세부 정보 및 복잡성을 숨겨 최소한의 코드로 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합 제품을 만들 수 있습니다.  
  
> [!WARNING]
>  관리되는 패키지 프레임워크 클래스를 포함하는 어셈블리는 대부분 Visual Studio SDK와 함께 제공됩니다.[프로젝트에 대한 관리되는 패키지 프레임워크](http://mpfproj11.codeplex.com/)에서 프로젝트에 대한 관리되는 패키지 프레임워크용 소스 코드를 다운로드할 수 있습니다.  
  
## MPF 네임스페이스  
 다음 표에서는 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)]에서 제공하는 MPF 네임스페이스 목록을 보여 줍니다.  
  
|네임스페이스|목차|  
|------------|--------|  
|<xref:Microsoft.VisualStudio>|COM 오류를 처리하기 위한 유용한 클래스, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 상수 및 Win32 창을 포함합니다.|  
|<xref:Microsoft.VisualStudio.Package>|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트, 편집기 및 MSBuild에 대한 관리 코드 래퍼를 포함합니다.|  
|<xref:Microsoft.VisualStudio.Shell>|일반적인 Visual Studio의 여러 개체의 구현을 파생할 수 있는 MPF 기본 클래스를 포함합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Design>|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 디자이너 확장을 포함합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Design.Serialization>|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] serialization 디자이너 확장을 포함합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Design.Serialization.CodeDom>|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] CodeDom 디자이너 확장을 포함합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Flavor>|프로젝트 하위 형식\("버전"\)을 지원합니다.|  
  
## 참고 항목  
 [VSPackage 및 관리 패키지 프레임워크](../misc/vspackages-and-the-managed-package-framework.md)   
 [Visual Studio Interop 어셈블리를 사용 하 여](../extensibility/internals/using-visual-studio-interop-assemblies.md)   
 [VSPackage 및 관리 패키지 프레임워크](../misc/vspackages-and-the-managed-package-framework.md)