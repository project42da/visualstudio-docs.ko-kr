---
title: 기타 파일 프로젝트 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- files, adding existing files to solutions
- Miscellaneous Files project
- Solution Items folder
- files, opening with Miscellaneous Files project
ms.assetid: 93a278a8-d4f4-400b-8945-4f1b0a2b5bac
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a637b37590a0aaf321a4e04896b2cbe12c29691f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="miscellaneous-files-project"></a>기타 파일 프로젝트
프로젝트 항목을 열려고 IDE에서 모든 항목을 솔루션의 모든 프로젝트의 구성원이 아닌 기타 파일 프로젝트에 할당 합니다.  
  
 사용자가 프로젝트 항목을 열 때 어떤 편집기를 사용 하는 결정 하는 데 중요 한 역할 프로젝트. 프로젝트 관련 편집기 또는 표준 편집기를 사용 하 여 특정 파일을 프로젝트를 디자인할 수 있습니다.  
  
 프로젝트 관련 편집기에는 일반적으로 사용자 특별 한 지식이 하거나 프로젝트에서 특별 한 인터페이스를 사용 하 여 필요 합니다. 자세한 내용은 참조 [하는 방법: 프로젝트 관련 편집기 열기](../../extensibility/how-to-open-project-specific-editors.md)합니다.  
  
 표준 편집기 프로젝트에서 특정 확장명의 파일을 열 수 있습니다. 사용자는 같은 일부 표준 편집기를 사용자 수는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트에 대 한 텍스트 편집기, 하지만 자신의 공용 문자를 유지 합니다. 표준 편집기를 사용 하 여 생성 됩니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 메서드.  
  
 프로젝트 항목을 열 수 있도록 응답 하는 솔루션의 프로젝트가 없는 경우 IDE는 모든 파일을 열고 기타 파일 프로젝트 라는 특수 한 프로젝트를 제공 합니다.  
  
 이 특수 한 프로젝트는 프로젝트의 컨텍스트 외부에서 파일 열기를 제공합니다. 처리 하는 동안는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenDocumentViaProject%2A> 메서드, 기타 파일 프로젝트 매우 낮은 우선 순위를 사용 하 여 항상 응답 합니다. 따라서 항상 기타 파일 프로젝트 파일을 열 수 있는 우선 순위가 높은 프로젝트에 생성 합니다.  
  
 기타 파일 프로젝트를 사용 하 여 명시적으로 만드는 사용자 필요 하지 않습니다는 **새 프로젝트** 대화 상자. 또한 기타 파일 프로젝트 프로젝트 팀 구성원의 목록의 영구적으로 관리 하지 않습니다. 각 사용자에 대해 가장 최근에 사용한 파일 목록을 기록 하려면 선택적 기능을 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument>   
 <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY>   
 [방법: 프로젝트 관련 편집기 열기](../../extensibility/how-to-open-project-specific-editors.md)   
 [방법: 표준 편집기 열기](../../extensibility/how-to-open-standard-editors.md)   
 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md)   
 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md)