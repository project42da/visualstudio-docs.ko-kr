---
title: "레거시 API를 사용 하 여 텍스트 레이어 액세스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - text layers
ms.assetid: 2258fcdd-38d1-479d-b8f8-1d4e6525f72c
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 8a5f7a80e8d594f3c9e62ecd2047cc1116948d2c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="accessing-text-layers-by-using-the-legacy-api"></a>레거시 API를 사용 하 여 텍스트 계층에 액세스
일반적으로 텍스트 레이어 텍스트 레이아웃의 일부 측면을 캡슐화합니다. 예를 들어 "함수에서-한 번" 레이어 캐럿 (텍스트 삽입 지점)이 포함 된 함수 앞뒤 텍스트를 숨깁니다.  
  
 텍스트 레이어 버퍼와 뷰 간에 있으며 뷰는 버퍼의 내용을 표시 하는 방식을 수정 합니다.  
  
## <a name="text-layer-information"></a>텍스트 계층 정보  
 다음 목록에는 텍스트 계층에서 작동 하는 방식을 설명 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]:  
  
-   구문 색 지정 및 표식이 있는 텍스트 계층에 있는 텍스트를 표시할 수 있습니다.  
  
-   현재 사용자 고유의 레이어를 구현할 수 없습니다.  
  
-   레이어 노출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer>에서 파생 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>합니다. 텍스트 버퍼 자체 기본 계층을 다형적으로 처리 하는 뷰를 사용 하면 계층으로도 구현 됩니다.  
  
-   레이어를 개수에 관계 없이 버퍼 및 보기 사이 수 있습니다. 각 계층을 하위 계층에만 하 고 보기 최상위 계층 대부분 처리 합니다. (보기에는 버퍼에 대 한 정보.)  
  
-   계층은 하위 계층만 발생할 수 있습니다. 표준 이벤트를 발생 초과 상위 계층에는 영향을 줄 수 없습니다.  
  
-   편집기에서 숨겨진된 텍스트, 합성 텍스트 및 줄 바꿈 계층으로 구현 됩니다. 레이어가 직접 상호 작용 하지 않고 숨겨진 / 합성 텍스트를 구현할 수 있습니다. 자세한 내용은 참조 [레거시 언어 서비스에서 개요](../extensibility/internals/outlining-in-a-legacy-language-service.md) 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsSyntheticTextSession>합니다.  
  
-   각 텍스트 레이어에를 통해 노출 되는 자체 로컬 좌표계는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer> 인터페이스입니다. 자동 줄 바꿈을 계층 예를 들어 고 포함할 수 있습니다 두 줄을 내부 텍스트 버퍼에는 한 줄만 포함 될 수 있습니다.  
  
-   계층을 통해 통신 하는 보기는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView> 인터페이스입니다. 이 인터페이스를 사용 하 여 버퍼 좌표로 좌표 보기를 조정 합니다.  
  
-   텍스트를 시작 하는 합성 텍스트 계층의 로컬 구현을 제공 해야와 같은 레이어 모든 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.CreateTrackingPoint%2A>합니다.  
  
-   외에 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer>, 텍스트 레이어를 구현 해야 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> 에서는 이벤트를 발생 하 고는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents> 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 편집기에서 색을 지정 하는 구문](../extensibility/syntax-coloring-in-custom-editors.md)   
 [텍스트 표식 레거시 API 사용](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [레거시 API를 사용 하 여 편집기 컨트롤 및 메뉴를 사용자 지정](../extensibility/customizing-editor-controls-and-menus-by-using-the-legacy-api.md)