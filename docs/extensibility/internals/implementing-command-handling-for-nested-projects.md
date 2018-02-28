---
title: "중첩 된 프로젝트에 대 한 처리 명령 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- nested projects, implementing command handling
ms.assetid: 48a9d66e-d51c-4376-a95a-15796643a9f2
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e4ed9efab34a51bdfaacea1773a33637437b2ced
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-command-handling-for-nested-projects"></a>중첩 된 프로젝트에 대 한 처리 명령 구현
IDE를 통해 전달 되는 명령에 전달할 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> 및 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스 부모 프로젝트 또는 중첩 된 프로젝트를 필터링 하거나 명령을 재정의할 수 있습니다.  
  
> [!NOTE]
>  일반적으로 부모 프로젝트에서 처리 하는 명령만 필터링 할 수 있습니다. 와 같은 명령 **빌드** 및 **배포** 에서 처리 하는 IDE를 필터링 할 수 없습니다.  
  
 다음 단계에서는 명령 처리를 구현 하기 위한 프로세스에 설명 합니다.  
  
## <a name="procedures"></a>절차  
  
#### <a name="to-implement-command-handling"></a>명령 처리를 구현 하려면  
  
1.  때 사용자는 중첩 된 프로젝트에서 중첩 된 프로젝트 또는 노드를 선택 합니다.  
  
    1.  IDE 호출은 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드.  
  
     — 또는 —  
  
    1.  IDE를 호출 하는 솔루션 탐색기에서 바로 가기 메뉴 명령 등의 계층 구조 창에서 명령을 발생 하는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> 메서드를 프로젝트의 부모입니다.  
  
2.  부모 프로젝트에 전달할 매개 변수를 검사할 수 `QueryStatus`와 같은 `pguidCmdGroup` 및 `prgCmds`, 부모 프로젝트 명령을 필터링 해야 하는지 여부를 확인 하려면. 부모 프로젝트 명령을 필터링 할 구현 되는 경우 설정 합니다.  
  
    ```  
    prgCmds[0].cmdf = OLECMDF_SUPPORTED;  
    // make sure it is disabled  
    prgCmds[0].cmdf &= ~MSOCMDF_ENABLED;  
    ```  
  
     부모 프로젝트를 반환 해야 하는 다음 `S_OK`합니다.  
  
     경우에 부모 프로젝트 명령을 필터링 하지 않습니다만 반환 해야 `S_OK`합니다. 이 경우 IDE 자동으로 라우팅하여 해당 명령을 자식 프로젝트에 있습니다.  
  
     부모 프로젝트 자식 프로젝트에 명령이 라우팅하 필요가 없습니다. 이 작업을 수행 하는 IDE...  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>   
 [명령, 메뉴 및 도구 모음](../../extensibility/internals/commands-menus-and-toolbars.md)   
 [프로젝트 중첩](../../extensibility/internals/nesting-projects.md)