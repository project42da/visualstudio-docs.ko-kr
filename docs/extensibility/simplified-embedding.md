---
title: "포함 하는 간소화 된 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], custom - simple view embedding
ms.assetid: f1292478-a57d-48ec-8c9e-88a23f04ffe5
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d4315a55b74d938576572b0630f5dca553643a24
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="simplified-embedding"></a>포함 하는 간소화 된
해당 문서 뷰 개체 (즉, 수행의 자식) 부모가 되는 경우 편집기에서 활성화 되어 단순화 포함 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> 인터페이스는 창 명령을 처리 하기 위해 구현 됩니다. 간단한 포함 편집기 활성 컨트롤을 호스트할 수 없습니다. 간소화 된 포함 된 편집기를 만드는 데 개체는 다음 그림에 표시 됩니다.  
  
 ![간단한 포함 편집기 그래픽](../extensibility/media/vssimplifiedembeddingeditor.gif "vsSimplifiedEmbeddingEditor")  
간단한 포함 편집기  
  
> [!NOTE]
>  만이 그림의 개체는 `CYourEditorFactory` 표준 파일 기반 편집기를 만드는 데 필요한 개체입니다. 사용자 지정 편집기를 만드는 경우 구현 하려면 않아도 됩니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2>편집기에는 자체 전용 지 속성 메커니즘이 있을 때문에 있습니다. 그러나 사용자 지정이 아닌 편집기에 대 한 해야 합니다.  
  
 에 포함 된 간소화 된 포함 된 편집기를 만들기 위해 구현 하는 모든 인터페이스는 `CYourEditorDocument` 개체입니다. 그러나 문서 데이터의 여러 뷰를 지원 하기 위해 분할 별도 데이터 및 보기 개체에 대 한 인터페이스는 다음 표에 나와 있는 것 처럼 합니다.  
  
|인터페이스|인터페이스의 위치|기능|  
|---------------|---------------------------|---------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|보기|부모 창에 대 한 연결을 제공합니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|보기|명령을 처리 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>|보기|상태 표시줄 업데이트를 사용하도록 설정합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser>|보기|수 있도록 **도구 상자** 항목입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEvents>|데이터|파일이 변경 될 때 알림을 보냅니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>|데이터|파일 형식에 대 한 이름으로 저장 기능을 사용 하도록 설정 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2>|데이터|문서에 대해 지속성을 사용하도록 설정합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl>|데이터|다시 로드 트리거 등의 파일 변경 이벤트의 제거를 허용합니다.|