---
title: "프로젝트 형식 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "새 프로젝트 형식"
  - "프로젝트 [Visual Studio SDK] 새 프로젝트 형식"
ms.assetid: bdb2d22e-d622-450c-bb2d-98152a745fcf
caps.latest.revision: 25
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 25
---
# 프로젝트 형식 만들기
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

확장할 수 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 새 프로젝트 형식을 만들어 합니다. 새 프로젝트 형식을 만들려면 몇 가지 개념을 이해 하 고 다양 한 단계를 완료 해야 합니다. 다음 항목에서는 프로젝트 유형을 만드는 방법에 대 한 개요를 제공 합니다.  
  
## 단원 내용  
 [프로젝트 형식에 대 한 설계 결정 사항](../../extensibility/internals/project-type-design-decisions.md)  
 항목, 프로젝트 파일 지 속성 및 새 프로젝트 형식을 만들기 전에 수행 해야 하는 약정 정비공 디자인 결정에 설명 합니다.  
  
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)  
 새 프로젝트 형식을 지 원하는 코드를 편집 하 고 컴파일, 빌드, 디버깅 및 프로젝트에서 응용 프로그램 배포로 프로그래밍 작업을 만들기 위해 수행 해야 하는 단계에 간략하게 설명 합니다.  
  
 [프로젝트 팩터리를 사용 하 여 프로젝트 인스턴스 만들기](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)  
 제공 하 고 새 프로젝트의 인스턴스를 만드는 프로젝트 팩터리를 사용 하는 방법에 대 한 정보를 제공 합니다.  
  
 [프로젝트 형식 등록](../../extensibility/internals/registering-a-project-type.md)  
 문 레지스트리에서 기본 경로 데이터를 테이블을 제공 하는 각 문에 대 한 레지스트리 스크립트에서 항목을 포함 하는 코드 샘플을 제공 합니다.  
  
 [프로젝트 지 속성](../../extensibility/internals/project-persistence.md)  
 사용을 설명 `IPersistFileFormat` 파일 및 프로젝트 파일 기반 개체를 모두 유지 하도록 합니다.  
  
 [MSBuild를 사용 하 여](../../extensibility/internals/using-msbuild.md)  
 프로젝트 형식을 사용 하는 방법을 설명는 [!INCLUDE[vstecmsbuild](../../extensibility/internals/includes/vstecmsbuild_md.md)] 엔진에서 작성 하는 사용자가 빌드 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 및 명령줄에서.  
  
## 관련 단원  
 [기호 검색 도구를 지원합니다.](../../extensibility/internals/supporting-symbol-browsing-tools.md)  
 보기 도구와 같은 코드의 아키텍처에 설명 된 **개체 브라우저** 및 **클래스 뷰** 창입니다. 인터페이스 및 VSPackage에서 개체 검색을 구현 하는 데 사용 되는 메서드를 설명 합니다.  
  
 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md)  
 프로젝트는 편집기 사용 하 여 프로젝트 항목을 열 때 결정을 수행 하는 중요 한 이유를 설명 합니다. 프로젝트 리소스를 어떻게 조작할 수 있습니다.  
  
 [Windows Installer를 사용 하 여 Vspackage를 설치](../../extensibility/internals/installing-vspackages-with-windows-installer.md)  
 VSPackage 자체 고유 id를 제공 하는 방법 및 Windows Installer 패키지에 VSPackage Dll 및 기타 정보를 래핑하는 방법을 보여 줍니다 \(합니다. MSI 파일\)를 고객에 게 배포 합니다.  
  
 [Visual Studio에서 계층 구조](../../extensibility/internals/hierarchies-in-visual-studio.md)  
 설명 어떻게 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 뷰와 주소 계층 구조입니다.  
  
 [Vspackage](../../extensibility/internals/vspackages.md)  
 VSPackage 확장 하는 설치 가능한 COM 개체에 간략하게는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 환경 고유의 VSPackage를 구현 하는 방법에 설명 합니다.  
  
 [프로젝트 형식](../../extensibility/internals/project-types.md)  
 코드를 수정, 컴파일 및 코드를 빌드 및 실행 하 고 디버깅할 코드 프로젝트를 사용 하는 방법에 설명 하 고 프로젝트 유형을 만들어야 하는 방법에 대 한 자세한 항목에 대 한 링크를 제공 합니다.