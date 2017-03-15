---
title: "방법: 실행 취소 스택을 지웁니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-실행 취소 스택에 지우기"
ms.assetid: 2200d2d4-7f58-401c-87fc-ddd32d368193
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# 방법: 실행 취소 스택을 지웁니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다음 절차를 실행 취소 스택을 지웁니다 방법을 설명 합니다.  
  
### 실행 취소 스택에 지우려면  
  
1.  실행 취소 스택 사용을 선택 취소 하는  [IOleUndoManager::DiscardFrom](http://msdn.microsoft.com/library/windows/desktop/ms693799) 메서드.  이러한 예는 다음과 같습니다.  
  
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
  
## 참고 항목  
 [방법: 실행 취소 관리 구현](../extensibility/how-to-implement-undo-management.md)