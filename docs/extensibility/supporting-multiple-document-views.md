---
title: "여러 문서 보기를 지원합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 사용자 지정-여러 문서 보기"
ms.assetid: c7ec2366-91c4-477f-908d-e89068bdb3e3
caps.latest.revision: 25
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 25
---
# 여러 문서 보기를 지원합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

문서 보기 개체와 별도 문서 데이터를 편집기를 작성 하 여 문서의 여러 보기를 제공할 수 있습니다.  추가 문서 보기 도움이 됩니다 몇 가지 경우가 있습니다.  
  
-   새 창 지원: 편집기에서 열 창을 가진 사용자를 선택 하 여 새 창을 열 수 있도록 같은 형식의 보기가 두 개 이상 제공할 수를 편집기를의  **새 창** 명령에서  **창** 메뉴.  
  
-   양식 및 코드 보기 지원: 편집기에 여러 종류의 보기를 제공 합니다.  [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]예를 들어, 폼 보기와 코드 보기를 모두 제공 합니다.  
  
 이 대 한 자세한 내용은 CreateEditorInstance 프로시저에서 Visual Studio 패키지 템플릿을 통해 만든 사용자 지정 편집기 프로젝트 EditorFactory.cs 파일을 참조 하십시오.  이 프로젝트에 대 한 자세한 내용은 참조 하십시오. [연습: 사용자 지정 편집기 만들기](../extensibility/walkthrough-creating-a-custom-editor.md).  
  
## 보기 동기화 중  
 여러 개의 뷰를 구현 하는 경우 문서 데이터 개체 모든 보기의 데이터와 동기화를 유지 하는 데 담당 합니다.  이벤트 인터페이스의 처리를 사용할 수 있습니다 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 여러 보기의 데이터와 동기화 합니다.  
  
 사용 하지 않는 경우 해당 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 문서 데이터 개체에 대 한 변경 내용을 처리 하도록 이벤트 시스템을 직접 구현 해야 하 고 여러 뷰를 동기화 할 개체입니다.  여러 뷰를 최신 상태로 유지 하려면 서로 다른 수준의 세분성 사용할 수 있습니다.  하나의 보기에서 입력할 때 최대 단위 설정과 다른 보기 즉시 업데이트 됩니다.  활성화 될 때까지 최소 단위와 다른 뷰가 업데이트 되지 않습니다.  
  
## 문서 데이터가 있는지 여부를 결정 합니다. 이미 열려  
 통합된 개발 환경 \(IDE\)에서 실행 중인 문서 테이블 \(RDT\) 데이터 문서에 대해 이미 다음 다이어그램에서와 같이 열려 있는지 여부를 추적 하는 데 도움이 됩니다.  
  
 ![DocDataView 그래픽](~/docs/extensibility/media/docdataview.gif "Docdataview")  
여러 보기  
  
 기본적으로 각 보기 \(문서 보기 개체\)는 자체 창 프레임에 포함 된 \(<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame>\).  이미 설명한 것 처럼, 문서 데이터가 여러 뷰를 표시할 수 있습니다.  이 기능을 사용 하려면 Visual Studio RDT 의심 문서 편집기에 열려 있는지 확인 하는 검사 합니다.  IDE 호출 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 편집기를 만들려면에서 NULL이 아닌 값이 반환의 `punkDocDataExisting` 매개 변수를 나타내는 문서가 이미 다른 편집기에 열려 있습니다.  RDT 함수 참조 하십시오 방법에 대 한 자세한 내용은 [실행 중인 Document 테이블](../extensibility/internals/running-document-table.md).  
  
 에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> 구현을 반환 된 문서의 데이터 개체를 검사 `punkDocDataExisting` 문서 데이터를 편집기에 적합 한지 여부를 결정 합니다.  \(예를 들어, HTML 데이터만 HTML 편집기가 나타납니다.\) 적절 한 경우 편집기 팩터리를 보기의 데이터를 제공 해야 합니다.  경우는 `punkDocDataExisting` 매개 변수가 아닌 `NULL`, 중 가능 문서 데이터 개체 다른 편집기에서 열기 또는 가능성이 있는지, 이미 문서 데이터 편집기 같은 다른 보기에서 열려 있습니다.  문서 데이터 편집기 팩터리를 지원 하지 않는 다른 편집기에 열려 있는 경우 Visual Studio 편집기 팩터리를 열지 못했습니다.  자세한 내용은 [방법: 뷰 문서 데이터를 연결 합니다.](../extensibility/how-to-attach-views-to-document-data.md)를 참조하십시오.