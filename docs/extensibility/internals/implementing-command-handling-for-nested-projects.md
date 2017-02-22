---
title: "중첩된 프로젝트에 대 한 처리 명령 구현 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "명령 처리를 구현 하는 중첩된 프로젝트"
ms.assetid: 48a9d66e-d51c-4376-a95a-15796643a9f2
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 중첩된 프로젝트에 대 한 처리 명령 구현
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

IDE를 통해 전달 되는 명령을 전달할 수 있습니다를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> 및 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스에 중첩 된 프로젝트 또는 부모 프로젝트 필터링 하거나 명령을 무시할 수 있습니다.  
  
> [!NOTE]
>  일반적으로 부모 프로젝트에서 처리 명령에만 필터링 할 수 있습니다.  명령으로 **Build** 및 **Deploy** 로 취급 됩니다 IDE를 필터링 할 수 없습니다.  
  
 다음 단계는 명령 처리를 구현 하는 프로세스에 설명 합니다.  
  
## 절차  
  
#### 명령 처리를 구현 하려면  
  
1.  때 사용자가 중첩 된 프로젝트에서 중첩된 프로젝트 노드 또는 노드 선택:  
  
    1.  IDE 호출을 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드가 있습니다.  
  
     —또는—  
  
    1.  IDE 명령 예: 솔루션 탐색기에서 바로 가기 메뉴 명령 계층 구조 창에서 시작 된 경우 호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> 에서 프로젝트의 부모 메서드.  
  
2.  부모 프로젝트에 전달할 매개 변수를 검사할 수 있습니다 `QueryStatus`, 같은 `pguidCmdGroup` 및 `prgCmds`, 부모 프로젝트의 명령을 필터링 해야 하는지 여부를 결정 합니다.  부모 프로젝트 명령을 필터링에 구현 되는 경우이 설정 해야 합니다.  
  
    ```  
    prgCmds[0].cmdf = OLECMDF_SUPPORTED;  
    // make sure it is disabled  
    prgCmds[0].cmdf &= ~MSOCMDF_ENABLED;  
    ```  
  
     부모 프로젝트를 반환 해야 하 고 `S_OK`.  
  
     부모 프로젝트 명령을 필터링 하지 않습니다 경우에 바로 반환 해야 `S_OK`.  이 경우 IDE 자동으로 명령을 하위 프로젝트를 회람합니다.  
  
     부모 프로젝트 명령 자식 프로젝트에 라우팅할 수 없습니다.  IDE이이 작업을 수행합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>   
 [명령, 메뉴 및 도구 모음](../../extensibility/internals/commands-menus-and-toolbars.md)   
 [중첩 프로젝트](../../extensibility/internals/nesting-projects.md)