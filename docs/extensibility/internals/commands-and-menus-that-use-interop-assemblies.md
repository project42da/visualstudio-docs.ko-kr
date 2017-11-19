---
title: "명령 및 메뉴 Interop 어셈블리를 사용 하는 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- menus, using interop assemblies
- interop assemblies, using in commands and menus
- commands, handling using interop assemblies
- command handling with interop assemblies
ms.assetid: 8f4af525-39e5-4e69-92c8-d3efabe80bb2
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ee9fa1faa52afb2ea6d8154b4767fcab2cee0981
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="commands-and-menus-that-use-interop-assemblies"></a>명령 및 Interop 어셈블리를 사용 하는 메뉴
Interop 어셈블리를 사용 하 여 메뉴 및 도구 모음 명령을 구현 하는 VSPackage 수행 해야 합니다.  
  
-   알릴는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 지 원하는 명령 및 현재 사용 여부에 대 한 통합된 개발 환경 (IDE).  
  
-   명령 처리에 대 한 규칙 (계약)을 따라야 합니다.  
  
-   명령 처리를 사용 하 여 명시적으로 구현 된 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> 인터페이스입니다.  
  
 이러한 작업을 수행 하는 방법을 설명 합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [Interop 어셈블리를 사용하여 명령 상태 결정](../../extensibility/internals/determining-command-status-by-using-interop-assemblies.md)  
 VSPackage는 IDE가 알리는 방법을 설명 합니다. 현재 사용 여부와 어떤 명령에 대 한 지원.  
  
 [Interop 어셈블리의 명령 계약](../../extensibility/internals/command-contracts-in-interop-assemblies.md)  
 Interop 어셈블리를 사용 하 여 명령을 구현 하는 모든 Vspackage에서 사용 하는 기본 명령 계약에 대 한 정의 제공 합니다.  
  
 [구현](../../extensibility/internals/command-implementation.md)  
 VSPackage는 명령을 구현 하는 방법을 간략하게를 설명 합니다.  
  
 [Interop 어셈블리 명령 처리기를 등록](../../extensibility/internals/registering-interop-assembly-command-handlers.md)  
 알릴 IDE는 VSPackage 명령 처리기를 제공 하는 데 필요한 레지스트리 항목에 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [가용성](../../extensibility/internals/command-availability.md)  
 사용할 수 있는 VSPackage 명령을 어떤 개체를 처리 하 고 확인 하는 IDE에서 사용 되는 조건을 설명 합니다.  
  
 [VSPackage에서 사용자 인터페이스 요소를 추가하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 사용 하는 UI를 만드는 방법에 대 한 세부 정보를 제공 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 명령을 지원 합니다.  
  
 [VSPackage의 명령 라우팅](../../extensibility/internals/command-routing-in-vspackages.md)  
 올바른 명령 요청을 가진 개체를 관련 시키기 위해 사용 되는 프로세스의 개요.