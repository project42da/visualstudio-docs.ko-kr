---
title: "방법: 실행 취소 스택을 지웁니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - clear undo stack
ms.assetid: 2200d2d4-7f58-401c-87fc-ddd32d368193
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e2592ad8bbec0ddf87731d25f5c46c714a3336d9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-clear-the-undo-stack"></a>방법: 실행 취소 스택을 지웁니다.
아래의 다음 절차에는 실행 취소 스택에 선택을 취소 하는 방법을 설명 합니다.  
  
### <a name="to-clear-the-undo-stack"></a>실행 취소 스택에 지우려면  
  
1.  실행 취소 스택을 사용을 선택 취소 하 고 [IOleUndoManager::DiscardFrom](http://msdn.microsoft.com/library/windows/desktop/ms693799) 메서드. 다음은 이러한 예입니다.  
  
    ```  
    HRESULT CCmdWindow::ClearUndoStack()  
    {  
      HRESULT hr = S_OK;  
  
      if (m_pUndoMgr == NULL)  
        {  
        IfFailGo(m_pTextLines->GetUndoManager(&m_pUndoMgr));  
        ASSERT(m_pUndoMgr != NULL, "",;);  
        }  
  
      IfFailGo(m_pUndoMgr->DiscardFrom(NULL));  
  
    Error:  
      return hr;  
    }  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [방법: 실행 취소 관리 구현](../extensibility/how-to-implement-undo-management.md)