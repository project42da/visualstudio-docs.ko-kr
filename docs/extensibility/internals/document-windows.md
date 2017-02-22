---
title: "문서 창 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Visual Studio SDK 문서 창"
ms.assetid: 50081d48-987f-43db-8bf9-51b7cf76e9c0
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# 문서 창
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Visual Studio에서는 *문서 창* 다중 문서 인터페이스 \(MDI\) 창에는 연관 된 자식 프레임된 창입니다. 디스플레이 및 소스 코드 또는 텍스트의 수정에 대 한 문서 창을 일반적으로 사용 하지만 다른 기능 종류를 호스팅할 수도 있습니다. 문서 창:  
  
-   동시에 여러 파일을 볼 수 있도록 MDI 부모에서 별도 가로 또는 세로 탭 그룹에 구성할 수 있습니다.  
  
-   MDI 부모에서 순서에 관계 없이 도킹 될 수 있습니다.  
  
-   자유롭게 이동할 수 있습니다.  
  
-   다른 MDI 창에 탭 순서에 연결 됩니다.  
  
 그룹화에 대 한 명령을, 도킹 및 부동 있습니다 문서 창의 탭에 대 한 바로 가기 메뉴.  
  
 Visual Studio에서 창 동작에 대 한 자세한 내용은 참조 [창 레이아웃 사용자 지정](../../ide/customizing-window-layouts-in-visual-studio.md)합니다.  
  
## 문서 창 구현  
 문서 창은 편집기를 구현 하 여 생성 됩니다.<xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> 인터페이스를 인스턴스화하는 편집기의 일부로 문서 창을 만듭니다. 자세한 내용은 [편집기에서 레거시 인터페이스](../../extensibility/legacy-interfaces-in-the-editor.md)을 참조하십시오.  
  
> [!NOTE]
>  뒤로 제공 하 고 창에서 탐색 포인트를 전달 하려면 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBackForwardNavigation> 인터페이스입니다. 텍스트 편집기 텍스트 표식을 사용 하 여 문서의 내용을 탐색을 식별 합니다.  
  
## 실행 Document 테이블  
 IDE 모든 문서 창의 상태를 추적 하는 실행 중인 document 테이블 \(RDT\)를 사용 합니다. RDT는 메커니즘 문서와 문서를 통해 windows의 파일을 편집한 후 나 솔루션을 닫을 때와 같은 이벤트 알림이 표시 됩니다. 자세한 내용은 [실행 중인 Document 테이블](../../extensibility/internals/running-document-table.md)을 참조하세요.  
  
## 참고 항목  
 [문서 로드를 지연합니다.](../../extensibility/internals/delayed-document-loading.md)