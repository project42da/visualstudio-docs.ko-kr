---
title: "프로젝트를 추가 하 고 프로젝트 항목 템플릿 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], adding
- project items [Visual Studio], adding
ms.assetid: 8c59217f-56e5-4540-a73b-cd10de189373
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1d0c9e684312468011f63bdfbb72d1cdadba6b08
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="adding-project-and-project-item-templates"></a>프로젝트 및 프로젝트 항목 템플릿 추가
표준을 사용 하 여 새 프로젝트 및 프로젝트 항목을 추가 하는 것에 대 한 지원을 제공 해야 사용자 고유의 프로젝트 형식을 만들 때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합 개발 환경 (IDE) 대화 상자. 다음 항목에는 프로젝트와 프로젝트 항목을 추가 하기 위한 다양 한 기술을 설명 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [프로젝트 컨텍스트](../../extensibility/internals/project-context.md)  
 프로젝트는 대부분의 환경에서 다소 기능에 대 한 컨텍스트 정보를 제공 하는지 설명 합니다.  
  
 [프로젝트 우선 순위](../../extensibility/internals/project-priority.md)  
 일반적으로 프로젝트 항목에 대 한 프로젝트에서 항목을 여는 데 사용 하는 모호성을 방지 하기 위해 한 프로젝트의 구성원 인지에 대해 설명 합니다.  
  
 [기타 파일 프로젝트](../../extensibility/internals/miscellaneous-files-project.md)  
 프로젝트가 프로젝트 항목을 열 때 사용할 편집기를 결정할 때 재생 두 유형의 파일을 열는 프로젝트 및 역할에 사용할 수 있는 편집기에 대 한 정보를 제공 합니다.  
  
 [프로젝트 템플릿 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)  
 수행 되는 동작에 대해 설명 때는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트가 만들어집니다.  
  
 [새 항목 추가 대화 상자에 항목 추가](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)  
 항목을 추가 하기 위한 프로세스에 설명 된 **새 항목 추가** 대화 상자.  
  
 [새 프로젝트 대화 상자에 디렉터리 추가](../../extensibility/internals/adding-directories-to-the-new-project-dialog-box.md)  
 사용자 지정 템플릿을 사용할 수 있는 VSPackage를 포함 하는 새 디렉터리를 등록 합니다. 예를 제공 합니다.  
  
 [새 항목 추가 대화 상자에 디렉터리 추가](../../extensibility/internals/adding-directories-to-the-add-new-item-dialog-box.md)  
 등록에 대 한 디렉터리의 새 집합의 예제를 제공는 **새 항목 추가** 대화 상자.  
  
 [프로젝트 시스템 확장을 위한 IDE 정의 명령](../../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)  
 다양 한 유형의 프로젝트 시스템을 확장 하는 데 사용 되는 명령 항목을 나열 합니다.  
  
 [일반적으로 프로젝트를 확장하는 데 사용되는 개체에 대한 CATID](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)  
 확장 하는 데 사용 되는 개체에 대 한 Catid를 나열 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)], [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)], 및 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 프로젝트 시스템.  
  
## <a name="related-sections"></a>관련 단원  
 [방법: 프로젝트별 편집기 열기](../../extensibility/how-to-open-project-specific-editors.md)  
 기본적으로 프로젝트에 대 한 특정 편집기에 바인딩된 항목을 열기 위한 단계별 지침을 제공 합니다.  
  
 [방법: 표준 편집기 열기](../../extensibility/how-to-open-standard-editors.md)  
 표준 편집기를 열기 위한 단계별 지침을 제공 합니다.  
  
 [프로젝트 하위 형식](../../extensibility/internals/project-subtypes.md)  
 하위 형식 개념 항목을 프로젝트에 대 한 링크를 제공 합니다. 기존 프로젝트 하위 형식 확장 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 및 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 프로젝트.  
  
 [프로젝트 형식](../../extensibility/internals/project-types.md)  
 새 프로젝트 형식을 디자인 하는 방법에 대 한 정보를 제공 하는 추가 항목 링크를 제공 합니다.