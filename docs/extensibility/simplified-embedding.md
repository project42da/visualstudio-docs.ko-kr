---
title: "간단한 포함 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK], 사용자 지정-단순 보기 포함"
ms.assetid: f1292478-a57d-48ec-8c9e-88a23f04ffe5
caps.latest.revision: 16
caps.handback.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
---
# 간단한 포함
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

단순화 된 포함 사용 편집기에 해당 문서의 뷰 개체 \(즉, 대 한 수의 자식\) 부모로 지정 되 면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> 는 인터페이스를 구현 하는 창 명령을 처리 합니다.  단순화 된 포함 편집기 활성 컨트롤을 호스팅할 수 없습니다.  편집기 단순화 포함을 만드는 데 사용 되는 개체는 다음 그림에 표시 됩니다.  
  
 ![간단한 포함 편집기 그래픽](../extensibility/media/vssimplifiedembeddingeditor.png "vsSimplifiedEmbeddingEditor")  
편집기로 단순화 포함  
  
> [!NOTE]
>  만이 그림의 개체는 `CYourEditorFactory` 표준 파일 기반 편집기를 만들기 위해 개체가 필요 합니다.  사용자 지정 편집기를 만드는 경우를 구현할 필요는 없습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2>, 자신의 개인 지 속성 메커니즘을 편집기 가능성이 없기 때문에.  그러나\-사용자 정의 편집기에 대 한, 그렇게 해야 합니다.  
  
 단순화 포함와 편집기를 만들기 위해 구현 된 모든 인터페이스에 포함 되어 있는 `CYourEditorDocument` 개체입니다.  그러나 문서 데이터의 다중 뷰를 지원 하려면 인터페이스 데이터 및 보기에 별도 개체에는 다음 표에 표시 된 대로 분할 합니다.  
  
|Interface|인터페이스의 위치|사용할 도구|  
|---------------|---------------|------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|보기|부모 창에 연결할을 수 있습니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|보기|명령을 처리합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>|보기|상태 표시줄 업데이트를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser>|보기|수 있도록  **도구** 항목입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEvents>|데이터|파일이 변경 되 면 알림을 보냅니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>|데이터|파일 형식에 대 한 다른 이름으로 저장 기능을 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2>|데이터|문서에 대 한 지 속성을 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl>|데이터|다시 로드를 트리거하는 것과 같이 파일 변경 이벤트를 억제 수 있습니다.|