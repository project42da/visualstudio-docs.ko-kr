---
title: 문서 창 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio SDK, document windows
ms.assetid: 50081d48-987f-43db-8bf9-51b7cf76e9c0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f2fd5b77bfc853da1c6098c00110e75b9d9acb75
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="document-windows"></a>문서 창
Visual Studio에서는 *문서 창* 프레임된 자식 창 (MDI) 다중 문서 인터페이스 기간과 연결 된입니다. 문서 기간을 표시 하 고의 소스 코드 또는 텍스트를 수정할 일반적으로 사용 하지만 다른 기능 형식의 호스트할 수 있습니다. 문서 창:  
  
-   동시에 여러 파일을 볼 수 있도록 MDI 부모에서 별도 가로 또는 세로 탭 그룹에 구성할 수 있습니다.  
  
-   MDI 부모에서 어떤 순서로 도킹 될 수 있습니다.  
  
-   자유롭게 이동할 수 있습니다.  
  
-   다른 MDI 창에 탭 순서에 연결 됩니다.  
  
 그룹화에 대 한 명령, 고정 및 고정 해제 있습니다 문서 창의 탭에 대 한 바로 가기 메뉴.  
  
 Visual Studio에서 창 동작에 대 한 자세한 내용은 참조 [창 레이아웃 사용자 지정](../../ide/customizing-window-layouts-in-visual-studio.md)합니다.  
  
## <a name="document-window-implementation"></a>문서 창 구현  
 문서 창은 편집기를 구현 하 여 생성 됩니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> 인터페이스 편집기 인스턴스화의 일환으로 문서 창을 만듭니다. 자세한 내용은 참조 [편집기에서 레거시 인터페이스](../../extensibility/legacy-interfaces-in-the-editor.md)합니다.  
  
> [!NOTE]
>  뒤로 제공에 전달 하는 창에서 탐색 포인트, 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBackForwardNavigation> 인터페이스입니다. 텍스트 편집기는 텍스트 표식을 사용 하 여 탐색은 문서의 내용을 식별 합니다.  
  
## <a name="the-running-document-table"></a>실행 중인 문서 테이블  
 IDE 실행 중인 문서 테이블 RDT ()를 사용 하 여 모든 문서 창의 상태를 추적 합니다. RDT는 문서를 통해 이벤트 파일을 편집한 후 또는 솔루션을 닫은 등의 windows 된다는 메커니즘입니다. 자세한 내용은 참조 [실행 중인 문서 테이블](../../extensibility/internals/running-document-table.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지연된 문서 로드](../../extensibility/internals/delayed-document-loading.md)