---
title: 기호 검색 도구를 지 원하는 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- symbols, symbol-browsing tools
- browsers, symbol browsers
- symbol-browsing tools
- libraries
- IVsLibrary2 interface, symbol-browsing tools
- IVsSimpleLibrary2 interface, symbol-browsing tools
- symbol-browsing tools, library manager
- symbols
- libraries, symbol-browsing tools
ms.assetid: 70d8c9e5-4b0b-4a69-b3b3-90f36debe880
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 08185f64310da610253dc35e69323b17ab0177fd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="supporting-symbol-browsing-tools"></a>기호 검색 도구를 지원합니다.
**개체 브라우저**, **클래스 뷰**, **호출 브라우저** 및 **기호 찾기 결과** 도구는 Visual Studio의 기능을 검색 하는 기호를 제공 합니다. 이러한 도구는 기호 중 한 계층 구조 트리 보기를 표시 하 고 트리에서 기호 사이의 관계를 보여 줍니다. 기호 네임 스페이스, 개체, 클래스, 클래스 멤버 및 다양 한 구성 요소에 포함 된 다른 언어 요소를 나타낼 수 있습니다. 구성 요소에는 Visual Studio 프로젝트의 경우 외부 포함 [!INCLUDE[dnprdnshort](../../code-quality/includes/dnprdnshort_md.md)] 구성 요소 및 라이브러리 (.tlb) 형식입니다. 자세한 내용은 [코드 구조 보기](../../ide/viewing-the-structure-of-code.md)를 참조하세요.  
  
## <a name="symbol-browsing-libraries"></a>기호 검색 라이브러리  
 언어 구현자로 구성 요소에서 기호를 추적 하 고 기호 목록 인터페이스 집합을 통해 Visual Studio 개체 관리자에 게 제공 하는 라이브러리를 만들어 Visual Studio 기호 검색 기능을 확장할 수 있습니다. 라이브러리에서 설명 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2> 인터페이스입니다. Visual Studio 개체 관리자 요청에 응답 새 데이터에 대 한 기호 검색 도구에서 라이브러리에서 데이터 가져오기 및 구성 하는 작업. 이후에 정보를 표시 하거나 요청 된 데이터와 도구를 업데이트 합니다. Visual Studio 개체 관리자에 대 한 참조를 가져오려면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2>, 전달는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsObjectManager> 서비스 ID에는 `GetService` 메서드.  
  
 각 라이브러리 모든 라이브러리에 정보를 수집 하는 Visual Studio 개체 관리자에 등록 해야 합니다. 라이브러리를 등록 하려면 호출 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> 메서드. 요청을 시작 하는 도구에 따라 Visual Studio 개체 관리자는 적절 한 라이브러리 찾아 데이터를 요청 합니다. 라이브러리 간에 전송 되는 데이터 및 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 에서 설명 하는 기호 목록에서 개체 관리자는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2> 인터페이스입니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 개체 관리자는 주기적으로 기호 검색 도구는 라이브러리에 포함 된 가장 최근 데이터를 반영 하도록 새로 고침에 대 한 합니다.  
  
 아래 다이어그램에는 샘플 라이브러리와 Visual Studio 개체 관리자 간의 요청/데이터 교환 프로세스의 주요 요소에 포함 되어 있습니다. 다이어그램에서 인터페이스는 관리 코드 응용 프로그램의 일부입니다.  
  
 ![데이터 흐름 라이브러리와 개체 관리자 간의](../../extensibility/internals/media/callbrowserdiagram.gif "CallBrowserDiagram")  
  
 기호 목록에는 Visual Studio 개체 관리자를 제공 하려면 먼저 등록 해야 라이브러리는 Visual Studio 개체 관리자를 호출 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> 메서드. 라이브러리를 등록 한 후 Visual Studio 개체 관리자 라이브러리의 기능에 대 한 특정 정보를 요청 합니다. 예를 들어 라이브러리 플래그를 요청 하 고 호출 하 여 범주를 지원는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2.GetLibFlags2%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2.GetSupportedCategoryFields2%2A> 메서드. 어느 시점 부터는이 라이브러리에서 데이터를 요청 하는 도구 중 하나 개체 관리자 요청 최상위 기호 목록이 호출 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2.GetList2%2A> 메서드. 에 대 한 응답 라이브러리 기호 목록에서 제조 및 Visual Studio 개체 관리자를 통해 노출 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2> 인터페이스입니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 개체 관리자를 호출 하 여 목록에 있는 항목 수를 결정은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetItemCount%2A> 메서드. 모든 다음 요청 목록에 지정 된 항목과 연결 하 고 각 요청에 항목 인덱스 번호를 지정 합니다. 호출 하 여 유형의 내게 필요한 옵션 및 항목의 다른 속성에 정보를 수집 하는 Visual Studio 개체 관리자 진행 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetCategoryField2%2A> 메서드.  
  
 호출 하 여 항목의 이름을 결정는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetTextWithOwnership%2A> 메서드를 호출 하 여 아이콘 정보를 요청 하 고는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetDisplayData%2A> 메서드. 아이콘의 항목 이름 왼쪽에 표시 되 고 항목의 내게 필요한 옵션 및 기타 속성의 형식을 보여 줍니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 개체 관리자는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetExpandable3%2A> 메서드를 지정 된 목록 항목을 확장할 수 있는 및 자식 항목을 확인 합니다. 개체 관리자를 호출 하 여 기호의 자식 목록을 요청 UI 요소를 확장 하는 요청을 보낸 경우에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetList2%2A> 메서드. 필요에 따라 작성 중인 트리의 다른 부분에서 프로세스가 계속 됩니다.  
  
> [!NOTE]
>  사용 하 여 네이티브 코드 기호 공급자를 구현 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsLibrary2> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectList2> 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 개체 관리자는 라이브러리를 등록 합니다.](../../extensibility/internals/how-to-register-a-library-with-the-object-manager.md)   
 [방법: 개체 관리자에는 라이브러리에서 제공 된 기호 목록을 노출](../../extensibility/internals/how-to-expose-lists-of-symbols-provided-by-the-library-to-the-object-manager.md)   
 [방법: 라이브러리의 기호 식별](../../extensibility/internals/how-to-identify-symbols-in-a-library.md)