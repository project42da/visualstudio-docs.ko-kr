---
title: "중첩된 프로젝트에 대 한 항목 추가 대화 상자를 필터링 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "필터링, 중첩된 프로젝트"
  - "중첩된 프로젝트 항목 추가 대화 상자 필터링"
ms.assetid: 5b3e352e-7f18-4f66-be16-b0ad55637ce5
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 중첩된 프로젝트에 대 한 항목 추가 대화 상자를 필터링
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

표시 된  **항목 추가** 대화 상자가 중첩 된 프로젝트의 부모 프로젝트 어떤 항목의 대화 상자에 표시 됩니다 제어할 수 있습니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2> 인터페이스를 사용 하면 필터링 됩니다 노드는  **항목 추가** 대화 상자.  때 하위 프로젝트가 표시 됩니다를  **항목 추가** 대화 상자의 부모를 구현할 수 있습니다는 `IVsFilterAddProjectItemDlg` 는 하위 프로젝트의 표시 될 인터페이스 및 필터 항목.  
  
 함수가 특정 상위 프로젝트 아래에 프로젝트를 그룹화 하면 구현할 수 있습니다 `IVsFilterAddProjectItemDlg` 사용자가 선택할 때  **프로젝트 항목 추가** 에서 중첩된 프로젝트 바로 가기 메뉴에서.  구현 `IvsFilterAddProjectItemDlg displays` 만 프로젝트 항목 또는 그룹에 특정 파일입니다.  같은 디렉터리에 저장 된 경우에 대화 상자를 프로젝트 항목을 다른 그룹에 대해 필터링 됩니다.  
  
 사용자가 열 때의  **항목 추가** 자식, 부모 프로젝트의 구현에 대 한 대화 상자를 `IVsFilterAddProjectItemDlg` 인터페이스를 호출할.  
  
 `IVsFilterAddProjectItemDlg` 범주에 따라 필터링 인터페이스 구현할 수도 있습니다.  자세한 내용은 [에 항목 추가 된 새 항목 추가 대화 상자](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md) 및 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [에 항목 추가 된 새 항목 추가 대화 상자](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)   
 [중첩 프로젝트](../../extensibility/internals/nesting-projects.md)