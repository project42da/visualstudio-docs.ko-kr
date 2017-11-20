---
title: "사용자 지정 편집기 및 디자이너를 만드는 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- designers [Visual Studio SDK]
- editors [Visual Studio SDK], custom
ms.assetid: b6a5e8b2-0ae1-4fc3-812d-09d40051b435
caps.latest.revision: "31"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 149870d9c9a0a281cb0bba167496cc4c37d6f83a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-custom-editors-and-designers"></a>사용자 지정 편집기 및 디자이너 만들기
Visual Studio 통합된 개발 환경 (IDE)는 다양 한 유형의 편집기를 호스팅할 수 있습니다.  
  
-   Visual Studio 핵심 편집기  
  
-   사용자 지정 편집기  
  
-   외부 편집기  
  
-   디자이너  
  
 다음 정보를 사용 하면 필요한 편집기의 유형을 선택 합니다.  
  
## <a name="types-of-editor"></a>편집기 유형  
 Visual Studio 핵심 편집기에 대 한 정보를 참조 하십시오. [편집기 및 언어 서비스 확장](../extensibility/extending-the-editor-and-language-services.md)합니다.  
  
##### <a name="custom-editors"></a>사용자 지정 편집기  
 사용자 지정 편집기는 특수 한 환경에서 작동 하도록 설계 되었습니다. 예를 들어 편집기 인 기능은 읽기 / 쓰기 데이터를 Microsoft Exchange server와 같은 특정 저장소를 하는 것을 만들 수 있습니다. 프로젝트 형식에만 사용 하는 편집기 또는 편집기 하려는 특정 명령의 수준을 가진 경우에 사용자 지정 편집기를 선택 합니다. 단, 사용자는 사용자 지정 편집기를 사용 하 여 표준 편집할 수 없습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트.  
  
 사용자 지정 편집기 편집기 팩터리를 사용할 수 있으며 편집기에 대 한 정보를 레지스트리에 추가 됩니다. 그러나 사용자 지정 편집기와 연관 된 프로젝트 형식을 다른 방법으로 사용자 지정 편집기를 인스턴스화할 수 있습니다.  
  
 사용자 지정 편집기 뷰를 구현 하 문제를 내부 활성화 또는 간소화 된 포함 하는 데 사용할 수 있습니다.  
  
##### <a name="external-editors"></a>외부 편집기  
 외부 편집기는 Microsoft Word, 메모장 또는 Microsoft FrontPage 같은 Visual Studio에 통합 되지 않은 편집기입니다. 예를 들어 전달 하는 텍스트를 VSPackage에서 하는 경우 이러한 편집기를 호출할 수 있습니다. 외부 편집기 등록 되며 Visual Studio 외부에서 사용할 수 있습니다. 외부 편집기를 호출 하는 호스 창에 포함 될 수 하는 경우 다음에 나타납니다 IDE의 창. 그렇지 않은 경우 IDE에 대 한 별도 창 만듭니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> 를 사용 하 여 문서의 우선 순위를 설정 하는 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> 열거형입니다. 경우는 `DP_External` 값을 지정한 경우 외부 편집기에서 파일을 열 수 있습니다.  
  
## <a name="editor-design-decisions"></a>편집기 디자인 관련 결정  
 다음 디자인 질문은 응용 프로그램에 적합 한 최상의 편집기의 종류를 선택할 수 데 도움이 됩니다.  
  
-   응용 프로그램의 데이터 파일에 저장할 여부? 데이터 파일에 저장 됩니다, 사용자 지정 또는 표준 형식에 있게 됩니다.  
  
     표준 파일 형식을 사용 하는 경우 프로젝트 뿐만 아니라 다른 프로젝트 형식을 열고 데이터를 읽기/쓰기 됩니다. 그러나 사용자 정의 파일 형식을 사용 하면 프로젝트 형식만를 열고 데이터를 읽기/쓰기 됩니다.  
  
     프로젝트 파일을 사용 하는 경우 다음 사용자 지정 해야 표준 편집기입니다. 프로젝트 파일을 사용 하지 않는 하지만 사용자 지정 편집기를 만들어야 합니다 데이터베이스 또는 다른 저장소에는 항목을 대신 사용 됩니다.  
  
-   ActiveX 컨트롤을 호스트 하 여 편집기에 필요 합니까?  
  
     편집기 ActiveX 컨트롤을 호스트 하는 경우 다음 구현에 내부 활성화 편집기에 설명 된 대로 [내부 활성화](../extensibility/in-place-activation.md)합니다. ActiveX 컨트롤을 호스팅하지 않는 경우 간단한 포함 편집기를 사용 하거나 사용자 지정의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 기본 편집기입니다.  
  
-   편집기는 여러 뷰를 지원? 기본 편집기로 동시에 표시 되도록 편집기 뷰를 원하는 경우에 여러 뷰를 지원 해야 합니다.  
  
     편집기를 여러 뷰를 지원 하는 경우 문서 데이터와 편집기에 대 한 문서 뷰 개체는 별도 개체 여야 합니다. 자세한 내용은 참조 [여러 문서 보기를 지 원하는](../extensibility/supporting-multiple-document-views.md)합니다.  
  
     편집기가 여러 뷰를 지 원하는 경우 계획 입니까 사용 하 여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 핵심 편집기의 텍스트 버퍼 구현 (<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 개체) 문서 데이터 개체에 대 한? 즉, 시겠습니까 프로그램 편집기 보기--와 함께 지원 하기 위해는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코어 편집기? 이 작업을 수행 하는 기능은 forms 디자이너의 기본...  
  
-   외부 편집기를 호스트 해야 하는 경우 편집기 포함할 수 있는 내부 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]?  
  
     포함할 수 있는 경우 호스트 창 외부 편집기에 대 한를 만들고 다음 호출에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> 집합과, 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> 열거형 값을 `DP_External`합니다. 편집기를 포함할 수 없는 경우 IDE에 대 한 별도 창을 자동으로 만듭니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [연습: 사용자 지정 편집기 만들기](../extensibility/walkthrough-creating-a-custom-editor.md)  
 사용자 지정 편집기를 만드는 방법에 설명 합니다.  
  
 [연습: 사용자 지정 편집기에 기능 추가](../extensibility/walkthrough-adding-features-to-a-custom-editor.md)  
 사용자 지정 편집기에 기능을 추가 하는 방법에 설명 합니다.  
  
 [디자이너 초기화 및 메타데이터 구성](../extensibility/designer-initialization-and-metadata-configuration.md)  
 디자이너를 초기화 하는 방법에 설명 합니다.  
  
 [디자이너에 실행 취소 지원 제공](../extensibility/supplying-undo-support-to-designers.md)  
 디자이너에 대 한 실행 취소 지원을 제공 하는 방법에 설명 합니다.  
  
 [사용자 지정 편집기의 구문 색 지정](../extensibility/syntax-coloring-in-custom-editors.md)  
 사용자 지정 편집기 및 코어 편집기에서 색을 지정 하는 구문의 차이점에 설명 합니다.  
  
 [사용자 지정 편집기의 문서 데이터 및 문서 보기](../extensibility/document-data-and-document-view-in-custom-editors.md)  
 사용자 지정 편집기에서 문서 데이터 및 문서 뷰를 구현 하는 방법에 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [편집기에서 레거시 인터페이스](../extensibility/legacy-interfaces-in-the-editor.md)  
 레거시 API를 사용 하 여 핵심 편집기에 액세스 하는 방법에 설명 합니다.  
  
 [레거시 언어 서비스 개발](../extensibility/internals/developing-a-legacy-language-service.md)  
 언어 서비스를 구현 하는 방법에 설명 합니다.  
  
 [Visual Studio의 다른 부분 확장](../extensibility/extending-other-parts-of-visual-studio.md)  
 나머지와 일치 하는 UI 요소를 만드는 방법에 설명 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory>