---
title: "방법: 연결 된 실행 취소 관리 사용 | Microsoft Docs"
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
  - "편집기 [Visual Studio SDK] 레거시-연결 된 실행 취소 관리"
ms.assetid: af5cc22a-c9cf-45b1-a894-1022d563f3ca
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# 방법: 연결 된 실행 취소 관리 사용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

연결 된 실행 취소 동시에 여러 파일에서 동일한 편집 작업을 취소할 수 있습니다.  예를 들어, 동시 텍스트 변경 내용을 Visual c \+ \+ 파일, 헤더 파일 등의 여러 프로그램 파일 전체에서 연결 된 실행 취소 트랜잭션을입니다.  실행 취소 관리자는 환경 구현으로 링크 된 실행 취소 기능 구성 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager> 이 기능을 조작할 수 있습니다.  연결 된 실행 취소 함께 하나의 실행 취소 단위로 처리 되 게 하려면 별도 실행 취소 스택에 연결할 수 있는 상위 실행 취소 단위에 의해 구현 됩니다.  연결 된 실행 취소를 사용 하는 절차는 다음 섹션에서 자세히 나와 있습니다.  
  
### 연결 된 실행 취소를 사용 하려면  
  
1.  Call `QueryService` on `SVsLinkedUndoManager` to get a pointer to `IVsLinkedUndoTransactionManager`.  
  
2.  호출 하 여 초기 부모 연결 된 실행 취소 단위를 만드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager.OpenLinkedUndo%2A>.  이 집합에 연결 된 실행 취소 스택이 그룹화 할 실행 취소 스택의 시작 지점을 설정 합니다.  에 있는 `OpenLinkedUndo` 방법을 엄격 하 게 또는 완전 하지 않은으로 링크 된 실행 취소 여부를 지정 하는 필요 합니다.  엄격 하지 않은 링크 된 실행 취소 동작을 하는 문서와 연결 된 실행 취소 형제 중 일부를 닫을 수 있습니다 여전히 다른 연결 된 상태로 두고 실행 취소 형제에 게 스택 있음을 의미 합니다.  엄격히 연결된 실행 취소 동작은 연결된 모든 실행 취소 형제 스택을 함께 실행 취소해야 하거나 아예 실행 취소하지 않도록 지정합니다.  후속 연결 취소 스택 호출 하 여 추가  [IOleUndoManager::Add](http://msdn.microsoft.com/library/windows/desktop/ms680135) 메서드가 있습니다.  
  
3.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager.CloseLinkedUndo%2A> 롤 중 하 나와 연결 된 실행 취소 단위를 모두 백업 합니다.  
  
    > [!NOTE]
    >  편집기에 연결 된 실행 취소 관리를 구현 하려면 실행 취소 관리를 추가 합니다.  연결 된 실행 취소 관리 구현에 대 한 자세한 내용은 참조 하십시오.  [방법: 실행 취소 구현 관리](../extensibility/how-to-implement-undo-management.md).  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>   
 [IOleParentUndoUnit](http://msdn.microsoft.com/library/windows/desktop/ms682151)   
 [IOleUndoUnit](http://msdn.microsoft.com/library/windows/desktop/ms678476)   
 [방법: 실행 취소 관리 구현](../extensibility/how-to-implement-undo-management.md)