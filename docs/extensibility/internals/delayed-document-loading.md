---
title: 문서 로드를 지연 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: fb07b8e2-a4e3-4cb0-b04f-8eb11c491f35
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dc10d7807633433b38fa8587d41c2ac3c0273ebe
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="delayed-document-loading"></a>문서 로드를 지연합니다.
사용자가 Visual Studio 솔루션을 대부분의 관련된 문서 즉시 로드 되지 않습니다. 문서 창 프레임 초기화 보류 중 상태에 만들어지고 (스텁 프레임 라고 함) 자리 표시자 문서에는 실행 중인 문서 테이블 (RDT)에 배치 됩니다.  
  
 확장은 프로젝트 문서를 로드 하기 전에 문서에 요소를 쿼리하여 불필요 하 게 로드 될 수 있습니다. Visual Studio에 대 한 전체 메모리 사용 공간을 늘릴 수이 합니다.  
  
## <a name="document-loading"></a>문서 로드  
 사용자가 액세스 문서의 예를 들어 창 프레임의 탭을 선택 하 여 스텁 프레임 및 문서 초기화 완벽 하 게 됩니다. RDT 문서 데이터를 얻기에 직접 액세스 하거나에 다음 호출 중 하나를 만들어 여는 RDT를 직접 액세스 하 여 문서의 데이터를 요청 하는 확장에서 문서를 초기화할 수도 있습니다.  
  
-   창 프레임 show 메서드: <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A>합니다.  
  
-   GetProperty 메서드 창 프레임 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> 다음 속성 중 하나:  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
 확장 프로그램에서 관리 되는 코드를 사용 하는 경우를 호출 하지 않아야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.GetDocumentInfo%2A> 되었음을 확인 하지 않는 한 문서에 보류 중인 초기화 상태를 없거나 완전히 초기화 될 문서... 이이 메서드는 항상 문서 반환 하기 때문에 데이터 개체를 만들어 필요한 경우. 대신 IVsRunningDocumentTable4 인터페이스에 방법 중 하나를 호출 해야 있습니다.  
  
 확장 프로그램에서 c + +를 사용 하는 경우 전달할 수 있습니다 `null` 않으려면 매개 변수에 대 한 합니다.  
  
 관련 속성에 대 한 하기 전에 다음 방법 중 하나를 호출 하 여 불필요 한 문서 로드를 방지할 수 있습니다: 다른 속성에 대 한 요청 전에 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID6>합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentFlags%2A>. 이 메서드가 반환 된 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4> 에 대 한 값을 포함 하는 개체 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4> 문서 아직 초기화 되지 않은 경우.  
  
 문서는 완전히 초기화 될 때 발생 하는 RDT 이벤트를 구독 하 여 문서 로드 되었을 때 찾을 수 있습니다. 두 가지 가능성이 있습니다.  
  
-   이벤트 싱크를 구현 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents2>를 구독할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents2.OnAfterAttributeChangeEx%2A>,  
  
-   그렇지 않으면 구독할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents.OnAfterAttributeChange%2A>합니다.  
  
 다음은 가상의 문서 액세스 시나리오입니다. 확장 프로그램에서 열려 있는 문서에 대 한 정보를 표시 하려면 Visual Studio, 예를 들어 편집 잠글 수 및 문서 데이터에 대 한 정보. 사용 하 여 RDT 문서 열거 <xref:Microsoft.VisualStudio.Shell.Interop.IEnumRunningDocuments>, 다음 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.GetDocumentInfo%2A> 편집 잠금 개수 및 문서 데이터를 검색 하기 위해 각 문서에 대 한 합니다. 문서 초기화 보류 중 상태에 있으면 문서 데이터를 요청 하면 불필요 하 게 초기화 됩니다.  
  
 이렇게 하면 보다 효율적이 사용 하는 것 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentEditLockCount%2A> 편집 잠금 수를 가져옵니다을 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentFlags%2A> 문서 초기화 되었는지 여부를 확인 하려면. 플래그는 포함 되지 않은 경우 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4>, 문서가 이미 초기화 된 문서 데이터를 요청 하 고 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentData%2A> 불필요 한 모든 초기화가 발생 하지 않습니다. 수행 된 플래그를 포함 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4>, 확장 문서 초기화 될 때까지 문서 데이터를 요청 하지 않아야 합니다. OnAfterAttributeChange(Ex) 이벤트 처리기에서이 검색할 수 있습니다.  
  
## <a name="testing-extensions-to-see-if-they-force-initialization"></a>초기화를 수행 하는 경우 이러한 참조에 대 한 확장 테스트  
 확장 프로그램에서 초기화 하는 경우 강제로 찾기 어려울 수 있도록 문서 초기화 되었는지 여부를 나타내는 시각적 없습니다 표시 있습니다. 텍스트 완전히 초기화 되지 않은 모든 문서 제목을 발생 하기 때문에 보다 쉽게 확인 하는 레지스트리 키를 설정할 수 있습니다 `[Stub]` 제목에서입니다.  
  
 **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\14.0\BackgroundSolutionLoad]**설정, **StubTabTitleFormatString** 를 **[스텁] {0}**합니다.