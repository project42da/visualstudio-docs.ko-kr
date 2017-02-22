---
title: "명령 및 Interop 어셈블리를 사용 하는 메뉴 | Microsoft Docs"
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
  - "interop 어셈블리를 사용 하 여 메뉴"
  - "명령 및 메뉴에서 사용 하는 interop 어셈블리"
  - "interop 어셈블리를 사용 하 여 처리 명령"
  - "interop 어셈블리를 처리 하는 명령"
ms.assetid: 8f4af525-39e5-4e69-92c8-d3efabe80bb2
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 명령 및 Interop 어셈블리를 사용 하는 메뉴
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

VSPackage interop 어셈블리를 사용 하 여 도구 모음 및 메뉴 명령을 구현 하는 다음 작업을 수행 해야 합니다.  
  
-   사용자에 게 알립니다는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 지 원하는 명령 및 현재 사용 여부에 대 한 통합된 개발 환경 \(IDE\).  
  
-   명령 처리 하는 것에 대 한 규칙 \(계약\)을 준수 합니다.  
  
-   명령 처리를 사용 하 여 명시적으로 구현 된 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> 인터페이스입니다.  
  
 이러한 작업을 수행 하는 방법을 설명 합니다.  
  
## 단원 내용  
 [Interop 어셈블리를 사용 하 여 명령 상태를 결정 합니다.](../../extensibility/internals/determining-command-status-by-using-interop-assemblies.md)  
 VSPackage IDE에 게 알리는 방법을 설명 합니다. 현재 사용 여부와 어떤 명령에 대 한 지원.  
  
 [Interop 어셈블리에 있는 명령 계약](../../extensibility/internals/command-contracts-in-interop-assemblies.md)  
 Interop 어셈블리를 사용 하 여 명령을 구현 하는 모든 Vspackage에서 사용 하는 기본 명령 계약에 대 한 정의 제공 합니다.  
  
 [구현](../../extensibility/internals/command-implementation.md)  
 VSPackage 명령을 구현 하는 방법의 개요를 제공 합니다.  
  
 [Interop 어셈블리 명령 처리기를 등록 하는 중](../../extensibility/internals/registering-interop-assembly-command-handlers.md)  
 VSPackage 명령 처리기를 제공 하는 IDE에 알리기 위해 필요한 레지스트리 항목에 설명 합니다.  
  
## 관련 단원  
 [가용성](../../extensibility/internals/command-availability.md)  
 VSPackage 명령을 사용할 수 있고 어떤 개체 처리를 결정 하는 IDE에서 사용 되는 조건을 설명 합니다.  
  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 사용 하는 UI를 만드는 방법에 대 한 세부 정보를 제공 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 명령을 지원 합니다.  
  
 [Vspackage의 명령 라우팅](../../extensibility/internals/command-routing-in-vspackages.md)  
 올바른 명령 요청 된 개체를 관련 시키기 위해 사용 되는 프로세스의 개요.