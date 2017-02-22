---
title: "문서 로드를 지연합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fb07b8e2-a4e3-4cb0-b04f-8eb11c491f35
caps.latest.revision: 6
caps.handback.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
---
# 문서 로드를 지연합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

사용자는 Visual Studio 솔루션을 닫았다가 다시 열거나, 대부분의 관련된 문서 즉시 로드 되지 않습니다. 문서 창 프레임의 초기화 보류 중 상태의 만들어지고 \(스텁 프레임\) 자리 표시자 문서에는 실행 중인 문서 테이블 \(RDT\)에 배치 됩니다.  
  
 확장은 프로젝트 문서를 로드 하기 전에 문서에 요소를 쿼리하여 불필요 하 게 로드 될 수 있습니다. Visual Studio에 대 한 전체 메모리 사용 공간이 높여도 합니다.  
  
## 문서 로드  
 사용자가 액세스 하면 문서를 예를 들어 창 프레임의 탭을 선택 하 여 스텁 프레임 및 문서 초기화 완벽 하 게 됩니다. 문서에 다음 호출 중 하나를 만들어는 RDT를 직접 액세스 하거나 RDT 문서 데이터를 얻기에 직접 액세스 하 여 문서의 데이터를 요청 하는 확장에 의해 초기화할 수도 있습니다.  
  
-   창 프레임 show 메서드: <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A>합니다.  
  
-   GetProperty 메서드 창 프레임 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> 다음 속성 중 하나:  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
 확장 프로그램에서 관리 코드를 사용 하는 경우 호출 하면 안 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.GetDocumentInfo%2A> 있는 것이 확실 하지 않으면 문서 초기화 보류 중 상태의 되었거나 완전히 초기화 될 문서... 이 메서드는 항상 문서 반환 하기 때문에이 필요한 경우 만드는 데이터 개체입니다. 대신 호출 해야 방법 중 하나는 IVsRunningDocumentTable4 인터페이스에.  
  
 확장 프로그램에서 c \+ \+를 사용 하는 경우 전달할 수 있습니다 `null` 원하지 않는 매개 변수입니다.  
  
 관련 속성에 대 한 요청 하기 전에 다음 방법 중 하나를 호출 하 여 불필요 한 문서 로드를 방지할 수 있습니다: 다른 속성에 대 한 요청 전에 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID6>합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentFlags%2A>. 이 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4> 에 대 한 값을 포함 하는 개체 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4> 문서 아직 초기화 되지 않은 경우.  
  
 문서는 완전히 초기화 될 때 발생 하는 RDT 이벤트를 구독 하 여 문서 로드 되었을 때 찾을 수 있습니다. 두 가지 가능성이 있습니다.  
  
-   이벤트 싱크를 구현 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents2>, 를 구독할 수 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents2.OnAfterAttributeChangeEx%2A>,  
  
-   그렇지 않으면 구독할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents.OnAfterAttributeChange%2A>합니다.  
  
 다음은 가상 문서 액세스 시나리오입니다. Visual Studio 확장에서 열린 문서에 대 한 일부 정보를 표시 하려면 예를 들어 편집 잠글 수 및 문서 데이터에 대 한 작업. 사용 하 여 RDT 문서 열거 <xref:Microsoft.VisualStudio.Shell.Interop.IEnumRunningDocuments>, 다음 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.GetDocumentInfo%2A> 편집 잠금 수 및 문서 데이터를 검색 하기 위해 각 문서에 대 한 합니다. 문서 초기화 보류 중 상태에 있으면 문서 데이터를 요청 하면 불필요 하 게 초기화 됩니다.  
  
 이렇게 더 효율적으로 사용 하 여 이것이 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentEditLockCount%2A> 을 편집 잠금 수를 가져오고 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentFlags%2A> 문서 초기화 되었는지 여부를 확인 하려면. 플래그는 포함 되지 않은 경우 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4>, 문서가 이미 초기화 된 문서 데이터를 요청 하 고 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentData%2A> 모든 불필요 한 초기화가 발생 하지 않습니다. 수행 된 플래그를 포함 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4>, 확장 문서 초기화 될 때까지 문서 데이터를 요청 하지 않아야 합니다. OnAfterAttributeChange\(Ex\) 이벤트 처리기에서이 검색할 수 있습니다.  
  
## 초기화를 수행 하는 경우 이러한 참조에 대 한 확장 테스트  
 확장 프로그램은 강제로 초기화 하는 경우 찾기 어려울 수 있도록 문서 초기화 되었는지 여부를 나타내기 위해 볼 수 없는 큐가 있습니다. 텍스트 완전히 초기화 되지 않은 모든 문서의 제목을 발생 하기 때문에 더 쉽게 확인 하는 레지스트리 키를 설정할 수 있습니다 `[Stub]` 제목에 있습니다.  
  
 **HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\14.0\\BackgroundSolutionLoad\]**, 설정, **StubTabTitleFormatString** 를 **{0} \[스텁\]**합니다.