---
title: "기호 검색 도구를 지원합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "기호를 기호 검색 도구"
  - "브라우저, 기호 브라우저"
  - "기호 검색 도구"
  - "라이브러리"
  - "IVsLibrary2 인터페이스, 기호 검색 도구"
  - "IVsSimpleLibrary2 인터페이스, 기호 검색 도구"
  - "기호 검색 도구, 라이브러리 관리자"
  - "기호"
  - "라이브러리, 도구 기호 검색"
ms.assetid: 70d8c9e5-4b0b-4a69-b3b3-90f36debe880
caps.latest.revision: 26
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 26
---
# 기호 검색 도구를 지원합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

**개체 브라우저**,  **클래스 뷰**,  **호출 브라우저** 및  **기호 찾기 결과** 도구는 검색 기능에서 Visual Studio 기호를 제공 합니다.  이러한 도구의 기호가 계층적 트리 뷰를 표시 하 고 기호 트리에서 사이의 관계를 표시 합니다.  기호를 네임 스페이스, 개체, 클래스, 클래스 멤버, 및 다양 한 구성 요소에 포함 된 다른 언어 요소를 나타낼 수 있습니다.  Visual Studio 프로젝트, 외부 구성 요소를 포함 [!INCLUDE[dnprdnshort](../../code-quality/includes/dnprdnshort_md.md)] 구성 요소 및 라이브러리 \(.tlb\) 형식입니다.  자세한 내용은 [코드 구조 보기](../../ide/viewing-the-structure-of-code.md)를 참조하십시오.  
  
## 기호 검색 라이브러리  
 언어 구현 자가와 기호에 구성 요소를 추적 하 고 기호 목록으로 Visual Studio 개체 관리자 인터페이스를 통해 제공 하는 라이브러리를 작성 하 여 Visual Studio 기호 검색 기능을 확장할 수 있습니다.  라이브러리에 설명 되어 있는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2> 인터페이스입니다.  Visual Studio 개체 관리자 요청에 대 한 새 데이터 기호 검색 도구에서 라이브러리에서 데이터를 받아 그 구성 응답 합니다.  그 후로 채웁니다 또는 도구가 요청 된 데이터를 업데이트 합니다.  Visual Studio 개체 관리자에 대 한 참조를 얻을 수 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2>, 전달의 <xref:Microsoft.VisualStudio.Shell.Interop.SVsObjectManager> ID로 서비스를 `GetService` 메서드.  
  
 각 라이브러리는 모든 라이브러리에는 정보를 수집 하는 Visual Studio 개체 관리자에 등록 해야 합니다.  호출 하는 라이브러리를 등록 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> 메서드.  도구는 요청 시작을 따라 Visual Studio 개체 관리자 적절 한 라이브러리를 검색 하 고 데이터를 요청 합니다.  라이브러리 간에 데이터를 이동 하 여 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 기호 설명 목록에서 개체 관리자는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2> 인터페이스입니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 개체 관리자 기호 검색 도구 라이브러리에 포함 된 최신 데이터를 반영 하도록 주기적으로 새로 고침에 대 한 책임이 있습니다.  
  
 아래 다이어그램에서는 라이브러리와 Visual Studio 개체 관리자 사이의 요청\/데이터 교환 프로세스의 주요 요소를 포함합니다.  다이어그램에 인터페이스를 관리 코드 응용 프로그램의 일부입니다.  
  
 ![라이브러리와 개체 관리자 간의 데이터 흐름](~/extensibility/internals/media/callbrowserdiagram.gif "CallBrowserDiagram")  
  
 기호 목록 Visual Studio 개체 관리자에 게 제공 하려면 먼저 라이브러리 Visual Studio 개체 관리자를 호출 하 여 등록 해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> 메서드가 있습니다.  라이브러리 등록 되 면 Visual Studio 개체 관리자 라이브러리의 기능에 대 한 특정 정보를 요청 합니다.  예를 들어 라이브러리 플래그를 요청 하 고 범주를 호출 하 여 지원 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2.GetLibFlags2%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2.GetSupportedCategoryFields2%2A> 방법입니다.  도구 중 하나이 라이브러리에서 데이터를 요청 하는 경우 일부 지점에서 개체 관리자 기호 목록의 최상위를 호출 하 여 요청을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2.GetList2%2A> 방법입니다.  응답, 라이브러리 기호 목록 제조 및 Visual Studio 개체 관리자를 통해 노출의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2> 인터페이스입니다.  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 개체 관리자를 호출 하 여 목록에 있는 항목 수를 결정을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetItemCount%2A> 메서드.  모든 다음 요청 목록에 지정 된 항목에 관련 된 및 각 요청에서 항목 인덱스 번호를 제공 합니다.  Visual Studio 개체 관리자를 호출 하 여 형식, 액세스 가능성, 및 항목의 다른 속성에 있는 정보를 수집 하는 진행 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetCategoryField2%2A> 메서드.  
  
 이 호출 하 여 항목의 이름을 결정은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetTextWithOwnership%2A> 메서드 아이콘 정보를 호출 하 여 요청을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetDisplayData%2A> 메서드.  아이콘이 항목 이름 왼쪽에 표시 되 고 항목, 액세스 가능성, 및 다른 속성의 형식을 보여 줍니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 관리자 호출 개체의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetExpandable3%2A> 지정 된 목록 항목을 확장할 수 있으며 하위 항목이 있는 경우 확인할 수 있는 방법은.  UI 요소를 확장 하는 요청을 보내는 경우에 객체 관리자를 호출 하 여 기호 하위 목록을 요청 합니다.의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetList2%2A> 메서드가 있습니다.  요청 시 빌드 중인 트리의 다른 부분에 프로세스를 계속 합니다.  
  
> [!NOTE]
>  사용 하는 네이티브 코드 기호 공급자를 구현 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsLibrary2> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectList2> 인터페이스.  
  
## 참고 항목  
 [방법: 개체 관리자와 함께 라이브러리를 등록 합니다.](../../extensibility/internals/how-to-register-a-library-with-the-object-manager.md)   
 [방법: 개체 관리자에는 라이브러리에서 제공 하는 기호 목록을 노출](../../extensibility/internals/how-to-expose-lists-of-symbols-provided-by-the-library-to-the-object-manager.md)   
 [방법: 라이브러리에 대 한 기호를 식별 합니다.](../../extensibility/internals/how-to-identify-symbols-in-a-library.md)