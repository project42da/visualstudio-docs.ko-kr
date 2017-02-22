---
title: "문서 잠금 소유자 관리 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK]-사용자 지정 문서 잠금"
ms.assetid: fa1ce513-eb7d-42bc-b6e8-cb2433d051d5
caps.latest.revision: 21
caps.handback.revision: 21
ms.author: "gregvanl"
manager: "ghogen"
---
# 문서 잠금 소유자 관리
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

실행 중인 문서 테이블 \(RDT\) 열려 있는 문서와 도구 들에서 편집 잠금을 유지 합니다.  이 프로그래밍 방식으로 백그라운드에서 사용자가 문서 윈도우에 열려 있는 문서를 볼 수 없는 편집할 때 편집 잠금 RDT는 문서에 배치할 수 있습니다.  이 기능은 그래픽 사용자 인터페이스를 통해 여러 개의 파일을 수정 하는 설계자가 자주 사용 됩니다.  
  
## 문서 잠금 소유자 시나리오  
  
### 파일 "a"가 "b" 파일에 대 한 종속성  
 표준 편집기 "A" 파일 형식에 대해 구현 하는 상황을 고려 "a"와 "a"가 한 참조 \(또는에 대 한 종속성\) 형식의 각 파일 형식의 "b" 합니다.  표준 편집기 "B" 파일 형식 "b"에 대 한 존재합니다.  편집기 "A" 파일을 열 때 "는" it "b"는 해당 파일에 대 한 참조를 검색 합니다.  파일을 "b" 표시 되지 않습니다, 하지만 편집기 "A"를 수정할 수 있습니다.  편집기 "A" 획득 문서 데이터 파일에 대 한 참조가 "b"에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> 메서드 또한 파일 "b"에 대 한 편집 잠금을 유지 관리 하 고 있습니다.  편집기 "A"가 완료 된 후 "파일 b 편집 잠금 감소" 수정 횟수 b 파일"에서"를 호출 하 여 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.UnlockDocument%2A> 메서드가 있습니다.  호출 해야 하는 경우이 단계를 생략할 수 있습니다의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> 메서드 매개 변수로 `dwRDTLockType` 설정 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS>.  
  
### "B" 파일을 다른 편집기에서 열  
 "A" 편집기 열기 하면 파일 "b" "B" 편집기에서 이미 열려 있습니다. 하는 경우, 두 가지 별도 시나리오를 처리할 수 있습니다.  
  
-   "B" 파일 호환 편집기에서 열려 있는 경우 "파일"b "를 사용 하 여 문서 편집 잠금 등록 편집기 A" 있어야 합니다의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.RegisterDocumentLockHolder%2A> 방법입니다.  수정 파일 "b"를 "A" 편집기를 마치면 등록 문서 편집 잠금 사용 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.UnregisterDocumentLockHolder%2A> 방법입니다.  
  
-   파일을 "b"를 호환 되지 않는 방식으로 열려 있는 경우 부분적으로 열기 및 표시 하는 오류 메시지 "A" 편집기와 연결 된 뷰 "는" 실패 또는 사용자가 편집기에서 시도한 열기 파일 "b"를 중 수 있습니다.  오류 메시지는 호환 되지 않는 편집기에 파일 "b"를 닫고 "a"를 사용 하 여 파일을 다시 열고 지시 합니다 "A" 편집기입니다.  수도 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 메서드 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable2.QueryCloseRunningDocument%2A> 호환 되지 않는 편집기에 열려 있는 파일을 "b"를 닫습니다 묻는 메시지를 합니다.  "A"에서 편집기 "A" 사용자 "b," 파일 열기 파일을 닫는 경우에 정상적으로 계속 됩니다.  
  
## 추가 문서 편집 잠금 고려 사항  
 또한 보유 하 고 있는 문서 편집기 "B" 것 보다 "b" 파일 잠금 편집 문서 있는 유일한 편집기 편집 잠금 파일 "b" 편집기 "A" 인 경우 서로 다른 동작을 볼 수 있습니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)],  **클래스 디자이너** 비주얼 디자이너에 연결 된 코드 파일 편집 잠금 보유 하지 않는 예제입니다.  즉, 디자인 보기에서 열고 클래스 다이어그램 사용자가 동시에 연결 된 코드 파일을 열 경우와 사용자 코드 파일을 수정 하면 변경 내용이 저장 되지 않습니다 또한에서 클래스 다이어그램 파일 \(.cd\)을 손실 됩니다.  경우는  **클래스 디자이너** 있는 유일한 문서 편집 잠금 코드 파일, 코드 파일을 닫을 때 변경 내용을 저장 하려면 묻는 메시지가 나타납니다지 않습니다.  IDE를 닫으면 변경 내용을 저장 하 라는  **클래스 디자이너**.  저장된 한 변경 내용은 두 파일 모두에 반영 됩니다.  두 경우에서  **클래스 디자이너** 코드 파일 편집기 라는 코드 파일 또는 폼을 닫을 때 저장 하 고 문서 편집 잠금 코드 파일을 보유 하 고 있습니다.  이때 저장 된 변경 내용은 양식과 코드 파일에 반영 됩니다.  클래스 다이어그램에 대 한 자세한 내용은 [Working with Class Diagrams \(Class Designer\)](../ide/working-with-class-diagrams-class-designer.md).  
  
 비\-편집기의 문서 편집 잠금 넣습니다 할 경우 반드시 구현 해야 참고는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder> 인터페이스입니다.  
  
 코드 파일을 프로그래밍 방식으로 수정 횟수는 UI 디자이너 하나 이상의 파일을 변경 합니다.  이러한 경우에는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell2.SaveItemsViaDlg%2A> 메서드를 저장 하는 방법으로 하나 이상의 문서 처리는  **다음 항목에 변경 내용을 저장 하 시겠습니까?** 대화 상자.  
  
## 참고 항목  
 [실행 중인 Document 테이블](../extensibility/internals/running-document-table.md)   
 [지 속성 및 실행 Document 테이블](../extensibility/internals/persistence-and-the-running-document-table.md)