---
title: "IVsPackage 인터페이스 구현 | Microsoft Docs"
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
  - "IVsPackage 인터페이스"
  - "인터페이스, IVsPackage 구현"
ms.assetid: 0c76b2e1-ce63-47fc-93ee-847cad281fc1
caps.latest.revision: 12
caps.handback.revision: 12
manager: "douge"
---
# IVsPackage 인터페이스 구현
모든 VSPackages 구현 해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> 인터페이스입니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]메서드를 호출 합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> 를 초기화 하 고 연결 된 속성 페이지를 보려면 VSPackages 닫기, 및 다른 이유로.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> 인터페이스 간의 게이트웨이 인터페이스입니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Vspackage를 하 고 있습니다.  
  
 관리 Vspackage의 하위 클래스로 작성할 수는 <xref:Microsoft.VisualStudio.Shell.Package> 클래스는 implements <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> 를 대신 하 여.  자세한 내용은 [관리되는 VSPackage](../misc/managed-vspackages.md)를 참조하십시오.  
  
> [!NOTE]
>  관리 되지 않는 샘플 코드 섹션의 Visual Studio 통합의 정도 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 는 ATL \(액티브 템플릿 라이브러리\)을 사용 하 여.  Vspackages를 만들려면 ATL을 사용 하지 않아도 되지만 ATL 샘플 코드를 잘 이해를 이해 해야 합니다.  
  
## 참고 항목  
 [Vspackage](../extensibility/internals/vspackages.md)