---
title: "IDE 정의 명령, 메뉴 및 그룹 | Microsoft Docs"
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
  - "명령, 환경 정의"
  - ".vsct 파일, 환경 정의 상수"
  - "명령 그룹, 환경 정의"
ms.assetid: 86b3af13-7163-48c6-986b-7beeedbc26cc
caps.latest.revision: 27
caps.handback.revision: 27
ms.author: "gregvanl"
manager: "ghogen"
---
# IDE 정의 명령, 메뉴 및 그룹
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

여러 메뉴, 명령 및 명령 그룹은 이미 정의에서 사용 하는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE입니다. 이러한 주석은 에서도 사용 가능한 확장 하는 경우 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
## 명령 환경 정의 찾기  
 환경 명령 4 개.vsct 파일 집합이 정의 되어 있습니다.  
  
-   SharedCmdDef.vsct  
  
-   SharedCmdPlace.vsct  
  
-   ShellCmdDef.vsct  
  
-   ShellCmdPlace.vsct  
  
 이러한 파일은 *\< Visual Studio SDK 설치 경로 \>*\\VisualStudioIntegration\\Common\\Inc\\ 합니다. 이러한 파일은 정 및 메뉴 및 메뉴, 그룹와 명령에 대 한 컨테이너로 VSPackage의 명령 테이블 구성 \(.vsct\) 파일에서 사용할 수 있는 그룹의 Guid를 제공 합니다.  
  
## 단원 내용  
 [Guid 및 Id의 Visual Studio 메뉴](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md)  
 Visual Studio 메뉴 모음에서 메뉴 및 포함 그룹의 GUID 및 ID 값을 제공 합니다.  
  
 [Guid 및 Visual Studio 도구 모음의 Id](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)  
 Visual Studio IDE에서 도구 모음 및 포함 그룹의 GUID 및 ID 값을 제공 합니다.  
  
 [Guid 및 Visual Studio 명령 Id](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md)  
 Visual Studio IDE에 의해 정의 된 명령 GUID 및 ID 값을 제공 합니다.  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [프로젝트 시스템 확장을 위한 IDE 정의 명령](../../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)   
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)