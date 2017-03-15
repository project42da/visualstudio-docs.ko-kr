---
title: "사용자 지정 편집기 및 디자이너 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디자이너 [Visual Studio SDK]"
  - "편집기 [Visual Studio SDK] 사용자 지정"
ms.assetid: b6a5e8b2-0ae1-4fc3-812d-09d40051b435
caps.latest.revision: 31
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 31
---
# 사용자 지정 편집기 및 디자이너 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 통합된 개발 환경 \(IDE\)는 다양 한 유형의 편집기를 호스트할 수 있습니다.  
  
-   Visual Studio 코어 편집기  
  
-   사용자 지정 편집기  
  
-   외부 편집기  
  
-   디자이너  
  
 다음 정보를 사용 하면 필요한 편집기의 유형을 선택 합니다.  
  
## 편집기의 형식  
 Visual Studio 코어 편집기에 대 한 정보를 참조 하십시오. [편집기 및 언어 서비스 확장](../extensibility/extending-the-editor-and-language-services.md)합니다.  
  
##### 사용자 지정 편집기  
 사용자 지정 편집기는 특수 한 환경에서 작동 하도록 설계 되었습니다. 예를 들어, 편집기 인 기능은 데이터 읽기 및 쓰기를 Microsoft Exchange server와 같은 특정 리포지토리에 하는 것을 만들 수 있습니다. 프로젝트 형식 에서만 작동 하는 편집기 또는 편집기 하려는 특정 명령의 수준을 가진 사용자 지정 편집기를 선택 합니다. 단, 사용자는 사용자 지정 편집기를 사용 하 여 표준 편집할 수 없습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트입니다.  
  
 사용자 지정 편집기 편집기 팩터리를 사용 하 고 편집기에 대 한 정보를 레지스트리에 추가할 수 있습니다. 그러나 사용자 지정 편집기와 연결 된 프로젝트 형식에는 다른 방법으로 사용자 지정 편집기를 인스턴스화할 수 있습니다.  
  
 사용자 지정 편집기 뷰를 구현 하 문제를 내부 활성화 또는 간소화 된 포함 하는 데 사용할 수 있습니다.  
  
##### 외부 편집기  
 외부 편집기는 Microsoft Word, 메모장 또는 Microsoft FrontPage 등 Visual Studio에 통합 되지 않은 편집기입니다. 예를 들어 전달 하는 텍스트를 VSPackage에서 하는 경우에 이러한 편집기를 호출할 수 있습니다. 외부 편집기 자신을 등록 하 고 Visual Studio 외부에서 사용할 수 있습니다. 외부 편집기를 호출 하는 호스 창에 포함 될 수 하는 경우 다음에 나타납니다 IDE의 창. 그렇지 않은 경우 다음 IDE에 대 한 별도 창을 만듭니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> 를 사용 하 여 문서의 우선 순위를 설정 하는 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> 열거형입니다. 하는 경우는 `DP_External` 값이 지정, 외부 편집기에서 파일을 열 수 있습니다.  
  
## 편집기 디자인 결정  
 다음 디자인 질문은 응용 프로그램에 적합 한 최상의 편집기의 유형을 선택 하는 데 도움이 됩니다.  
  
-   응용 프로그램의 데이터 파일에 저장할 여부? 해당 데이터 파일에 저장 하기, 사용자 지정 또는 표준 형식 수는?  
  
     표준 파일 형식을 사용 하면 프로젝트 외에 다른 프로젝트 형식과 열고 데이터를 읽기\/쓰기 됩니다. 사용자 지정 파일 형식을 사용 하는 경우, 프로젝트 형식만 유지할 수 있지만를 열고 데이터를 읽기\/쓰기입니다.  
  
     프로젝트 파일을 사용할 경우 다음 사용자 지정 해야 표준 편집기입니다. 프로젝트 파일을 사용 하지 않습니다 하지만 대신 사용자 지정 편집기를 만들어야 합니다 데이터베이스 또는 다른 저장소에서 항목을 사용 합니다.  
  
-   편집기에 ActiveX 컨트롤을 호스트 해야 합니까?  
  
     편집기에서 ActiveX 컨트롤을 호스트 하는 경우 다음 구현 내부 활성화 편집기에 설명 된 대로 [현재 위치에서 활성화](../misc/in-place-activation.md)합니다. ActiveX 컨트롤을 호스팅하지 않을 경우 한 다음 간단한 포함 편집기를 사용 하거나 사용자 지정은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 기본 편집기입니다.  
  
-   편집기는 여러 뷰를 지원 합니까? 뷰 편집기의 기본 편집기로 동시에 표시 되도록 하려는 경우에 여러 뷰를 지원 해야 합니다.  
  
     편집기를 여러 뷰를 지원 해야 하는 경우 문서 데이터와 문서 뷰 개체의 편집기에 대 한 별도 개체 여야 합니다. 자세한 내용은 [여러 문서 보기를 지원합니다.](../extensibility/supporting-multiple-document-views.md)을 참조하십시오.  
  
     편집기에서 여러 보기를 지 원하는 경우 하려는 사용 하는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 편집기의 텍스트 버퍼 구현 핵심 \(<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 개체\) 문서 데이터 개체에 대 한? 즉, 시겠습니까 프로그램 편집기 보기\-\-와 함께 지 원하는 데는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코어 편집기? 이 작업을 수행 하는 기능은 forms 디자이너의 기본...  
  
-   외부 편집기를 호스트 해야 하는 경우 수 편집기 내부에 포함 될 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]?  
  
     포함 될 경우 호스트 창 외부 편집기를 만들고 다음 호출에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> 메서드 집합과 <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> 열거형 값을 `DP_External`합니다. 편집기를 포함할 수 없는 경우 IDE에 대 한 별도 창을 자동으로 만듭니다.  
  
## 단원 내용  
 [연습: 사용자 지정 편집기 만들기](../extensibility/walkthrough-creating-a-custom-editor.md)  
 사용자 지정 편집기를 만드는 방법에 설명 합니다.  
  
 [연습: 추가 기능을 사용자 지정 편집기로](../extensibility/walkthrough-adding-features-to-a-custom-editor.md)  
 사용자 지정 편집기 기능을 추가 하는 방법에 설명 합니다.  
  
 [디자이너 초기화 및 메타 데이터 구성](../extensibility/designer-initialization-and-metadata-configuration.md)  
 디자이너를 초기화 하는 방법에 설명 합니다.  
  
 [디자이너 작업 취소 지원 제공](../extensibility/supplying-undo-support-to-designers.md)  
 디자이너에 대 한 실행 취소 지원을 제공 하는 방법에 설명 합니다.  
  
 [사용자 지정 편집기에서 색을 지정 하는 구문](../extensibility/syntax-coloring-in-custom-editors.md)  
 코어 편집기와 사용자 지정 편집기 색을 지정 하는 구문의 차이점에 설명 합니다.  
  
 [문서 데이터와 사용자 지정 편집기에서 문서 보기](../extensibility/document-data-and-document-view-in-custom-editors.md)  
 사용자 지정 편집기의 문서 데이터 및 문서 보기를 구현 하는 방법에 설명 합니다.  
  
## 관련 단원  
 [편집기에서 레거시 인터페이스](../extensibility/legacy-interfaces-in-the-editor.md)  
 기존 API를 사용 하 여 핵심 편집기에 액세스 하는 방법에 설명 합니다.  
  
 [언어 서비스 개발](../extensibility/internals/developing-a-legacy-language-service.md)  
 언어 서비스를 구현 하는 방법에 설명 합니다.  
  
 [Visual Studio의 다른 부분을 확장합니다.](../extensibility/extending-other-parts-of-visual-studio.md)  
 나머지와 일치 하는 UI 요소를 만드는 방법에 설명 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory>