---
title: 소스 제어를 지 원하는 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control [Visual Studio SDK], supporting
ms.assetid: 567acde3-354e-4f39-8d99-0ef86c103396
caps.latest.revision: 18
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: f5dd2a98ec84b656dc70a00236775710266c54ba
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="supporting-source-control"></a>소스 제어를 지원합니다.
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]파일 체크 아웃, 체크 인 및 프로젝트 또는 편집기에 대해 다른 소스 제어 작업을 지원합니다. 소스 제어 클라이언트도 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 와 같은 원본 제어 패키지와 상호 작용 하도록 설계 되었습니다 [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)], 보관, 버전 관리 및 동적으로 정의 된 파일 집합에 대 한 제어 기능도 제공 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [소스 제어 패키지 모델](../../extensibility/internals/model-for-source-control-packages.md)  
 프로젝트 형식을 구현 해야 하는 인터페이스를 설명 합니다. 소스 제어를 지원 하도록 합니다.  
  
 [설계 결정 사항](../../extensibility/internals/source-control-design-decisions.md)  
 해당 대답 프로젝트 형식이 구현 하는 방법을 변경 하는 질문을 제공 합니다.  
  
 [구성 세부 정보](../../extensibility/internals/source-control-configuration-details.md)  
 소스 제어를 지 원하는 프로젝트 형식 구현을 변경 하는 방법을 설명 합니다.  
  
 [프로젝트 및 편집기에 대 한 추가 지침](../../extensibility/internals/additional-source-control-guidelines-for-projects-and-editors.md)  
 프로젝트 형식 및 편집기에 대 한 모범 사례를 설명합니다.  
  
 [런타임 세부 정보](../../extensibility/internals/source-control-runtime-details.md)  
 소스 제어 시스템에 추가 하는 경우 프로젝트를 등록 하는 방법을 설명 합니다.  
  
## <a name="reference"></a>참조  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>  
 환경 또는 메모리에서 변경 되거나 저장 될 파일은 소스 제어 패키지에 알립니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>  
 프로젝트 및 계층을 소스 제어로 자신을 등록 하 고 소스 제어 상태에 대 한 정보를 얻을 수 있습니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>  
 프로젝트 파일 및 프로젝트 항목에 대 한 소스 제어를 제공 하는 프로젝트 시스템에서 구현 됩니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>  
 프로젝트에서 추가, 제거 또는 파일 또는 디렉터리를 솔루션의 이름을 바꿀 수 있는 권한 환경 쿼리 하는 데 사용 합니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>  
 클라이언트를 프로젝트 파일이 나 디렉터리에 대 한 변경 내용에 알립니다.  
  
## <a name="related-sections"></a>관련 단원  
 [프로젝트 형식](../../extensibility/internals/project-types.md)  
 기본 빌딩 블록으로 프로젝트에 대 한 개요를 제공는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE). 프로젝트 빌드 및 코드 컴파일를 제어 하는 방법을 설명 하는 추가 항목 링크가 제공 됩니다.