---
title: "소스 제어를 지원합니다. | Microsoft Docs"
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
  - "컨트롤 [Visual Studio SDK]를 지 원하는 원본"
ms.assetid: 567acde3-354e-4f39-8d99-0ef86c103396
caps.latest.revision: 18
caps.handback.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
---
# 소스 제어를 지원합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]파일 체크 아웃, 체크 인 및 기타 소스 제어 작업을 편집기 또는 프로젝트를 지원합니다.  소스 제어 클라이언트는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 같은 소스 제어 패키지와 상호 작용 하도록 설계 되었습니다 [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)], 보관, 버전 지정 및 제어 기능을 동적으로 정의 된 파일 집합에 대해 설명 합니다.  
  
## 단원 내용  
 [소스 제어 패키지에 대 한 모델](../../extensibility/internals/model-for-source-control-packages.md)  
 프로젝트 형식에서 구현 해야 하는 인터페이스에 설명 합니다. 소스 제어를 지원 합니다.  
  
 [설계 결정 사항](../../extensibility/internals/source-control-design-decisions.md)  
 그와 관련 된 프로젝트 형식을 구현 하는 방법을 변경 하는 질문을 제공 합니다.  
  
 [구성 세부 정보](../../extensibility/internals/source-control-configuration-details.md)  
 소스 제어를 지 원하는 프로젝트 형식의 구현을 변경 되는 방식에 대해 설명 합니다.  
  
 [프로젝트 및 편집기에 대 한 추가 지침](../../extensibility/internals/additional-source-control-guidelines-for-projects-and-editors.md)  
 프로젝트 형식 및 편집기에 대 한 최상의 방법을 설명 합니다.  
  
 [런타임 세부 정보](../../extensibility/internals/source-control-runtime-details.md)  
 프로젝트는 소스 제어 시스템에 사용자를 추가 하면 등록 하는 방법을 설명 합니다.  
  
## 참조  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>  
 환경 또는 파일 메모리에서 변경 하거나 저장할 수 있는 소스 제어 패키지를 나타냅니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>  
 프로젝트와 함께 소스 제어에 자동으로 등록 하 고 소스 제어 상태에 대 한 정보를 얻을 수 있는 계층 수 있습니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>  
 소스 제어 프로젝트 파일 및 프로젝트 항목에 대해 제공 하는 프로젝트 시스템을 구현 합니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>  
 프로젝트에서 환경에 대 한 추가, 제거 또는 파일 또는 솔루션의 디렉터리 이름을 바꿀 수 있는 쿼리를 사용 합니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>  
 프로젝트 파일이 나 디렉터리에 대 한 변경 내용 클라이언트를 게 알립니다.  
  
## 관련 단원  
 [프로젝트 형식](../../extensibility/internals/project-types.md)  
 프로젝트의 기본 빌딩 블록으로 개요는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\)입니다.  프로젝트 빌드 및 코드 컴파일을 제어 하는 방법에 대해 설명 하는 추가 항목 링크 제공.