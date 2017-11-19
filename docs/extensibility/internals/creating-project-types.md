---
title: "프로젝트 형식 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project types, new
- projects [Visual Studio SDK], new project types
ms.assetid: bdb2d22e-d622-450c-bb2d-98152a745fcf
caps.latest.revision: "25"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f7c0bba9b80e4e874f222ce00834f44a2d93e3e7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-project-types"></a>프로젝트 형식 만들기
확장할 수 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 새 프로젝트 형식을 만들어 합니다. 새 프로젝트 형식을 만들려는 몇 가지 개념을 이해 하 고 몇 가지 단계를 완료 해야 합니다. 다음 항목 프로젝트 유형을 만드는 방법에 대 한 개요를 제공 합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [프로젝트 형식 디자인 결정](../../extensibility/internals/project-type-design-decisions.md)  
 항목, 프로젝트 파일 지 속성 및 새 프로젝트 형식을 만들기 전에 수행 해야 하는 약속 정비 디자인 결정에 설명 합니다.  
  
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)  
 새 프로젝트 형식을 지 원하는 코드를 편집 및 컴파일할 빌드, 디버깅 및 프로젝트에 응용 프로그램 배포로 프로그래밍 작업을 만들기 위해 수행 해야 하는 단계에 간략하게 설명 합니다.  
  
 [프로젝트 팩터리를 사용하여 프로젝트 인스턴스 만들기](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)  
 제공 하 고 새 프로젝트의 인스턴스를 만들 프로젝트 팩터리를 사용 하는 방법에 대 한 정보를 제공 합니다.  
  
 [프로젝트 형식 등록](../../extensibility/internals/registering-a-project-type.md)  
 레지스트리에서 테이블의 기본 경로 데이터를 제공 하는 포함 하는 문은 각 문에 대 한 레지스트리 스크립트에서 항목의 코드 예제를 제공 합니다.  
  
 [프로젝트 지속성](../../extensibility/internals/project-persistence.md)  
 사용을 설명 `IPersistFileFormat` 파일과 프로젝트 파일 기반 개체를 모두 유지 하도록 합니다.  
  
 [MSBuild 사용](../../extensibility/internals/using-msbuild.md)  
 프로젝트 형식을 사용 하 여 방법에 대해 설명 된 [!INCLUDE[vstecmsbuild](../../extensibility/internals/includes/vstecmsbuild_md.md)] 빌드 엔진에서 작성 하는 사용자가을 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 및 명령줄에서.  
  
## <a name="related-sections"></a>관련 단원  
 [기호 검색 도구 지원](../../extensibility/internals/supporting-symbol-browsing-tools.md)  
 보기 도구와 같은 코드의 아키텍처에 설명 된 **개체 브라우저** 및 **클래스 뷰** 창. 인터페이스 및 VSPackage에서 개체 검색을 구현 하는 데 사용 되는 메서드를 설명 합니다.  
  
 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md)  
 프로젝트에서 프로젝트 항목을 열 때 편집기 사용 되었는지 확인 하는 중요 한 이유를 설명 있으며 어떻게 프로젝트 리소스를 조작할 수 있습니다.  
  
 [Windows Installer를 사용하여 VSPackage 설치](../../extensibility/internals/installing-vspackages-with-windows-installer.md)  
 Windows Installer 패키지에서 VSPackage Dll 및 기타 정보를 줄 바꿈 하는 VSPackage는 자체의 고유한 id를 지정 하는 방법을 보여 줍니다 (합니다. MSI 파일)를 고객에 게 배포 합니다.  
  
 [Visual Studio의 계층 구조](../../extensibility/internals/hierarchies-in-visual-studio.md)  
 설명 방법을 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 뷰와 주소 계층 구조입니다.  
  
 [VSPackage](../../extensibility/internals/vspackages.md)  
 설치 가능한 COM 개체를 확장 하는 VSPackage의 개요를 제공는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 환경 사용자 고유의 VSPackage를 구현 하는 방법에 설명 합니다.  
  
 [프로젝트 형식](../../extensibility/internals/project-types.md)  
 프로젝트 코드를 수정, 컴파일 및 코드를 빌드 및 실행 하 고 디버깅할 코드를 사용 하는 방법에 설명 하 고 프로젝트 유형을 만들어야 하는 방법에 대 한 자세한 항목에 대 한 링크를 제공 합니다.