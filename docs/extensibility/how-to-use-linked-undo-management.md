---
title: "방법: 연결 된 실행 취소 관리를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - linked undo management
ms.assetid: af5cc22a-c9cf-45b1-a894-1022d563f3ca
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 05e10305f7e4c243f799cfe33d4d9b86418eed86
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-use-linked-undo-management"></a>방법: 연결 된 실행 취소 관리 사용
연결 된 실행 취소를 동시에 여러 파일에 같은 편집 작업을 취소할 수 있습니다. 예를 들어 헤더 파일 및 Visual c + + 파일을 같은 여러 프로그램 파일에 걸쳐 동시 텍스트가 변경 되는 연결 된 실행 취소가 트랜잭션입니다. 환경의 구현의 실행 취소 관리자에 연결 된 실행 취소 기능이 내장 되어 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager> 이 기능을 조작할 수 있습니다. 연결 된 실행은 별도 실행 취소 스택에 실행 취소 단일 단위로 취급 되어야 하는 함께 연결할 수 있는 부모 실행 취소 단위를 통해 구현 됩니다. 연결 된 실행을 사용 하는 절차는 다음 섹션에 자세히 설명 되어 있습니다.  
  
### <a name="to-use-linked-undo"></a>연결 된 실행을 사용 하려면  
  
1.  호출 `QueryService` 에 `SVsLinkedUndoManager` 에 포인터를 얻으려면 `IVsLinkedUndoTransactionManager`합니다.  
  
2.  호출 하 여 초기 부모 연결 된 실행 취소 단위를 만들 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager.OpenLinkedUndo%2A>합니다. 이 실행 취소 스택에 연결 된 실행 취소 스택을으로 그룹화 할 수 하의 집합에 대 한 시작 지점을 설정 합니다. 에 `OpenLinkedUndo` 메서드 strict 또는 비 엄격한 되도록 연결 된 실행 취소 여부를 지정 해야 합니다. 비를 엄격 하 게 연결 된 실행 취소 동작 일부 연결 된 실행 취소가 형제가 있는 문서를 닫을 수 및 연결 된 다른 leave 취소할 여 스택과에 형제를 의미 합니다. 엄격 하 게 연결 된 실행 취소 동작 모든 연결 된 실행 취소가 형제 스택에 함께 되지 않거나 전혀 실행 취소할 수 해야 함을 지정 합니다. 연결 된 후속 실행 취소 스택을 호출 하 여 추가 [IOleUndoManager::Add](http://msdn.microsoft.com/library/windows/desktop/ms680135) 메서드.  
  
3.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager.CloseLinkedUndo%2A> 롤백하기 위해 모든 하나로 연결 된 실행 취소 단위입니다.  
  
    > [!NOTE]
    >  편집기에 연결 된 실행 취소 관리를 구현 하려면 실행 취소 관리를 추가 합니다. 연결 된 실행 취소 관리 구현에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 실행 취소 관리 구현](../extensibility/how-to-implement-undo-management.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>   
 [IOleParentUndoUnit](http://msdn.microsoft.com/library/windows/desktop/ms682151)   
 [IOleUndoUnit](http://msdn.microsoft.com/library/windows/desktop/ms678476)   
 [방법: 실행 취소 관리 구현](../extensibility/how-to-implement-undo-management.md)