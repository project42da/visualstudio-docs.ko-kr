---
title: 여러 문서 뷰를 지 원하는 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - multiple document views
ms.assetid: c7ec2366-91c4-477f-908d-e89068bdb3e3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 78ddc7ed811086622454e31d12ca5f1324d00da5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="supporting-multiple-document-views"></a>여러 문서 보기를 지원합니다.
편집기에 대 한 별도 문서 데이터 및 문서 보기 개체를 만들어 문서의 둘 이상의 보기를 제공할 수 있습니다. 추가 문서 보기는 유용할 수 있는 몇 가지 경우가 있습니다.  
  
-   새 창 지원: 이미 창이 편집기에서 열려 있는 사용자가을 선택 하 여 새 창을 열 수 있도록 동일한 형식의 두 개 이상의 보기를 제공 하 여 편집기를 원하는 **새 창** 명령을 **창** 메뉴.  
  
-   폼 및 코드 뷰 지원: 다양 한 종류의 보기를 제공 하 여 편집기를 원하는 합니다. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]예를 들어 폼 보기와 코드 보기를 제공 합니다.  
  
 이 대 한 자세한 내용은 Visual Studio 패키지 템플릿으로 만든 사용자 지정 편집기 프로젝트의 EditorFactory.cs 파일의 CreateEditorInstance 절차를 참조 합니다. 이 프로젝트에 대 한 자세한 내용은 참조 [연습: 사용자 지정 편집기 만들기](../extensibility/walkthrough-creating-a-custom-editor.md)합니다.  
  
## <a name="synchronizing-views"></a>뷰를 동기화합니다.  
 여러 뷰를 구현 하는 경우 문서 데이터 개체는 데이터와 동기화 하는 모든 보기를 유지 하는 일을 담당 합니다. 이벤트 인터페이스에 처리를 사용할 수 있습니다 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 여러 뷰 데이터와 동기화 합니다.  
  
 사용 하지 않는 경우는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 문서 데이터 개체에 대 한 변경 내용을 처리 하도록 사용자 고유의 이벤트 시스템을 구현 해야 하는 다음 여러 뷰를 동기화 하는 개체입니다. 여러 뷰를 최신 상태로 유지 하는 다른 세분화 수준을 사용할 수 있습니다. 최대 세분성을 설정 하 여 하나의 보기에 입력할 때 다른 뷰가 즉시 업데이트 됩니다. 최소 단위와 다른 보기 활성화 될 때까지 업데이트 되지 않습니다.  
  
## <a name="determining-whether-document-data-is-already-open"></a>문서 데이터 여부를 결정 하는 이미 열려 있습니다.  
 통합된 개발 환경 (IDE)에서 실행 중인 문서 테이블 (RDT)에 다음 다이어그램에 나와 있는 것 처럼 문서에 대 한 데이터가 이미 열려 있는지 여부를 추적 하는 데 도움이 됩니다.  
  
 ![DocDataView 그래픽](../extensibility/media/docdataview.gif "Docdataview")  
다중 뷰  
  
 기본적으로 각 보기 (문서 보기 개체)는 자체 창 프레임에 포함 (<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame>). 그러나 이미 설명한 것 처럼 문서 데이터 표시할 수 있습니다에 여러 보기. 이 작업이 가능 하도록 Visual Studio에 문서는 이미 편집기에서 열려 있는지 여부를 확인 하려면 RDT를 확인 합니다. IDE 호출 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 편집기를 만들려면 NULL이 아닌 값에 반환 된 `punkDocDataExisting` 문서 문서가 이미 다른 편집기에서 열려 있다고 매개 변수를 나타냅니다. 방법에 대 한 자세한 내용은 RDT 함수 참조 [실행 중인 문서 테이블](../extensibility/internals/running-document-table.md)합니다.  
  
 사용자 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> 구현에서 반환 된 문서 데이터 개체를 검사 `punkDocDataExisting` 문서 데이터 편집기에 대 한 적절 한 되는지 확인 하려면. (예를 들어 HTML 데이터만 표시 되어서는 HTML 편집기에서.) 적절 한 이면 편집기 팩터리 데이터에 대 한 두 번째 보기를 제공 해야 합니다. 경우는 `punkDocDataExisting` 매개 변수가 않습니다 `NULL`,이 가능한 문서 데이터 개체로 다른 편집기에에서 열려 또는 인지, 가능성이, 문서 데이터는 이미 다른 보기와 같은 편집기에서에서 열려 있습니다. 문서 데이터 편집기 팩터리를 지원 하지 않는 다른 편집기에서 열려 있으면 Visual Studio 편집기 팩터리를 열려는 실패 합니다. 자세한 내용은 참조 [하는 방법: 문서 데이터 연결 보기](../extensibility/how-to-attach-views-to-document-data.md)합니다.