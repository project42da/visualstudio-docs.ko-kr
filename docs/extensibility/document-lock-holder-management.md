---
title: 문서 잠금 소유자 관리 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - document locking
ms.assetid: fa1ce513-eb7d-42bc-b6e8-cb2433d051d5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 65f5a38f5d4da0986b7f95c9287a94e657efa9c5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="document-lock-holder-management"></a>문서 잠금 소유자 관리
실행 중인 문서 테이블 (RDT) 열려 있는 문서와 있는 모든 편집 잠금을의 개수를 유지 합니다. 문서 창에 열려 있는 문서를 표시 하는 사용자 없이 백그라운드에서 프로그래밍 방식으로 편집 될 때 문서는 RDT에 대해 편집 잠금을 배치할 수 있습니다. 이 기능은 그래픽 사용자 인터페이스를 통해 여러 파일을 수정 하는 디자이너에서 자주 사용 됩니다.  
  
## <a name="document-lock-holder-scenarios"></a>문서 잠금 소유자 시나리오  
  
### <a name="file-a-has-a-dependence-on-file-b"></a>파일 "a"에 파일에 대 한 종속성 "b"  
 파일 형식에 대 한 "A" 표준 편집기를 구현 하는 경우를 가정해 봅시다 "a"와 각 파일 형식에 대 한 참조 (또는에 대 한 종속성) "a"가 "b" 형식의 파일입니다. 표준 편집기 "B"는 "b" 형식의 파일에 존재합니다. "A" 편집기 파일을 여는 경우 "a" it "b"는 해당 파일에 대 한 참조를 검색 합니다. 파일이 "b", 표시 되지 않은 있지만 편집기 "A"에서 수정할 수 있습니다. 편집기 "A" 파일의 문서 데이터에 대 한 참조 "b"에서 가져옵니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> 메서드 "b" 파일에 대 한 편집 잠금을 유지 하 고 있습니다. "A" 편집기를 완료 한 후 파일 "b"를 호출 하 여 계산 수정 파일 "b" 편집 잠금 감소 시킬 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.UnlockDocument%2A> 메서드. 호출한 것이 단계를 생략할 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> 메서드 매개 변수와 함께 `dwRDTLockType` 로 설정 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS>합니다.  
  
### <a name="file-b-is-opened-by-a-different-editor"></a>다른 편집기에서 "b" 파일을 열  
 파일 "b"으로 이미 열려 편집기 "B" 편집기 "A" 열려고 할 때, 두 가지 별도 시나리오를 처리 하 합니다.  
  
-   편집기 "A" 사용 하 여 "b" 파일에 대 한 문서 편집 잠금을 등록 있어야 "b" 파일을 호환 되는 편집기에서 열려 있는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.RegisterDocumentLockHolder%2A> 메서드. 등록을 취소 문서를 사용 하 여 잠금을 편집 수정 하 고 파일 "b" 편집기 "A"를 완료 한 후의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.UnregisterDocumentLockHolder%2A> 메서드.  
  
-   파일 "b"를 호환 되지 않는 방식으로 열려 있으면 "A" 실패 또는 있습니다 하도록 "A" 부분적으로 열고 적절 한 오류 메시지를 표시 하는 편집기와 연결 된 뷰 편집기에서 파일 "b"를 시도한 열기를 하도록 하거나 있습니다. 오류 메시지를 호환 되지 않는 편집기에서 파일 "b"를 닫고 다시 사용 하 여 "a" 파일을 엽니다 사용자를 지시 해야 편집기 "A"입니다. 구현할 수도 있습니다는 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 메서드 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable2.QueryCloseRunningDocument%2A> 호환 되지 않는 편집기에 열려 있는 사용자 "b" 파일을 닫습니다. 사용자가 "b", 여는 파일의 파일을 닫을 경우에 "a" 편집기 "A" 정상적으로 계속 합니다.  
  
## <a name="additional-document-edit-lock-considerations"></a>추가 문서 편집 잠금 고려 사항  
 "A" 편집기 "B" 편집기도 문서를 저장 하는 것 보다 "b" 파일에 대 한 잠금을 편집 하는 문서에 있는 유일한 편집기에서 편집할 파일 "b"에 대 한 잠금을 다른 동작이 얻을 수 있습니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], **클래스 디자이너** 은 연결된 된 코드 파일에서 편집 잠금을 유지 하지 않는 비주얼 디자이너의 예입니다. 즉, 사용자가 디자인 뷰에서 열 클래스 다이어그램 및 연결된 된 코드 파일을 동시에, 열 및 사용자 코드 파일을 수정 했지만 변경 내용을 저장 하지 않는 경우 변경 내용이 손실 됩니다 클래스 다이어그램 (.cd) 파일에. 경우는 **클래스 디자이너** 에 문서 편집 코드 파일에 대 한 잠금을, 사용자가 하지 하 라는 메시지가 표시 코드 파일을 닫을 때 변경 내용을 저장 합니다. 사용자가을 닫은 후에 변경 내용을 저장 하 라는 메시지를 IDE는 **클래스 디자이너**합니다. 두 파일에 저장 된 변경 내용은 반영 됩니다. 모두는 **클래스 디자이너** 사용자 코드 파일 또는 폼을 닫을 때 저장할지 묻는 코드 파일 편집기에서 코드 파일에 대해 문서 편집 잠금을 보유 합니다. 해당 시점에 변경 내용은 저장된 양식과 코드 파일에 반영 됩니다. 클래스 다이어그램에 대 한 자세한 내용은 참조 하십시오. [클래스 다이어그램 (클래스 디자이너) 작업](../ide/working-with-class-diagrams-class-designer.md)합니다.  
  
 비 편집기에 대 한 문서에 대 한 편집 잠금을 배치 해야 하는 경우 구현 해야 한다는 참고는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder> 인터페이스입니다.  
  
 여러 번 UI 디자이너 코드 파일을 프로그래밍 방식으로 수정 하는 여러 개의 파일을 변경 합니다. 이러한 경우에는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell2.SaveItemsViaDlg%2A> 방법으로 하나 이상의 문서를 저장 하는 처리는 **다음 항목에 변경 내용을 저장 하 시겠습니까?** 대화 상자.  
  
## <a name="see-also"></a>참고 항목  
 [실행 중인 문서 테이블](../extensibility/internals/running-document-table.md)   
 [지속성 및 실행 중인 문서 테이블](../extensibility/internals/persistence-and-the-running-document-table.md)