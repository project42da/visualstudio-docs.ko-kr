---
title: "중첩 된 프로젝트에 대 한 항목 추가 대화 상자를 필터링 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- filtering, nested projects
- nested projects, AddItem dialog box filtering
ms.assetid: 5b3e352e-7f18-4f66-be16-b0ad55637ce5
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e1f5fc7695df028330d0e53faebefc178f499da1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="filtering-the-additem-dialog-box-for-nested-projects"></a>중첩 된 프로젝트에 대 한 필터링 항목 추가 대화 상자
표시할 때는 **AddItem** 중첩 된 프로젝트의 경우 부모 프로젝트 대화 상자 대화 상자에 표시 되는 항목을 제어할 수 있습니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2> 인터페이스를 사용 하면에 있는 노드를 필터링 한 **AddItem** 대화 상자. 자식 프로젝트 표시 될 때는 **AddItem** 대화 상자에서 부모를 구현할 수는 `IVsFilterAddProjectItemDlg` 자식 프로젝트에 표시 되는 인터페이스 및 필터 항목입니다.  
  
 구현할 수 있습니다 프로젝트에서는 부모 프로젝트에서 함수에 의해 그룹화 되 `IVsFilterAddProjectItemDlg` 선택 **프로젝트 항목 추가** 중첩 된 프로젝트의 바로 가기 메뉴. 구현 `IvsFilterAddProjectItemDlg displays` 만 프로젝트 항목 또는 파일 그룹에 특정 합니다. 다른 그룹에 대 한 프로젝트 항목은 동일한 디렉터리에 저장 되는 경우에 대화 상자에서 필터링 됩니다.  
  
 사용자가 열 때는 **AddItem** 부모 프로젝트의 구현 자식에 대 한 대화 상자는 `IVsFilterAddProjectItemDlg` 인터페이스가 호출 됩니다.  
  
 `IVsFilterAddProjectItemDlg` 인터페이스 범주별으로 필터링을 구현할 수도 있습니다. 자세한 내용은 참조 [새 항목 추가 대화 상자에 항목 추가](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md) 및 [등록 프로젝트 및 항목 템플릿](../../extensibility/internals/registering-project-and-item-templates.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [항목에 추가 된 새 항목 추가 대화 상자](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)   
 [프로젝트 중첩](../../extensibility/internals/nesting-projects.md)