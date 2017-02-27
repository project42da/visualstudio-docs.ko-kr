---
title: "레거시 API를 사용 하 여 텍스트 레이어 액세스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-텍스트 레이어"
ms.assetid: 2258fcdd-38d1-479d-b8f8-1d4e6525f72c
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# 레거시 API를 사용 하 여 텍스트 레이어 액세스
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

일반적으로 텍스트 레이어에 텍스트 레이아웃의 일부 기능을 캡슐화합니다.  예를 들어, "함수에서\-번" 레이어 캐럿 \(텍스트 삽입 지점\)를 포함 하는 함수 앞뒤 텍스트를 숨깁니다.  
  
 텍스트 레이어 버퍼와 보기 사이 고 보기 버퍼의 내용을 보는 방법으로 수정 됩니다.  
  
## 텍스트 레이어 정보  
 다음 목록에서 텍스트 레이어를 어떻게 설명 합니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]:  
  
-   텍스트 레이어의 텍스트 구문 색상 표시 및 표식으로 표시 될 수 있습니다.  
  
-   현재 레이어를 직접 구현할 수 없습니다.  
  
-   레이어를 노출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer>에서 파생 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>.  또한 텍스트 버퍼 레이어 보기 밑에 있는 레이어가 함께 다형적으로 처리할 수 있도록 구현 됩니다.  
  
-   원하는 만큼 레이어 보기와 버퍼 간에 겹쳐질 수 있습니다.  각 레이어를 아래 레이어로 처리 및 보기 맨 위에 있는 레이어를 주로 다룹니다.  \(보기 버퍼에 대 한 몇 가지 정보가 필요.\)  
  
-   계층은 하위 계층에만 영향을 줍니다.  표준 이벤트 발생 하는 이상 그 위에 있는 레이어에 영향을 줄 수 없습니다.  
  
-   편집기에서 숨겨진된 텍스트, 합성 텍스트와 줄 바꿈 계층으로 구현 됩니다.  텍스트 숨김 및 합성 레이어를 직접 상호 작용 하지 않고 구현할 수 있습니다.  자세한 내용은 [레거시 언어 서비스 개요](../extensibility/internals/outlining-in-a-legacy-language-service.md) 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsSyntheticTextSession>을 참조하십시오.  
  
-   각 텍스트 레이어를 통해 노출 되는 자체 로컬 좌표계가 있는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer> 인터페이스입니다.  내부 버퍼가 텍스트 한 줄만 포함 될 수 있습니다 있지만 자동 줄 바꿈을 레이어, 예를 들어, 두 줄 포함 될 수 있습니다.  
  
-   보기를 통신 레이어를 통과 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView> 인터페이스입니다.  이 인터페이스를 사용 하 여 버퍼 좌표와 좌표 보기를 조정 합니다.  
  
-   텍스트 발생 한 합성 텍스트 레이어는 로컬 구현을 제공 해야 합니다 같은 원하는 레이어 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.CreateTrackingPoint%2A>.  
  
-   외에 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer>, 텍스트 레이어를 구현 해야 합니다 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> 에서 발생 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents> 인터페이스.  
  
## 참고 항목  
 [사용자 지정 편집기에서 색을 지정 하는 구문](../extensibility/syntax-coloring-in-custom-editors.md)   
 [레거시 API와 함께 텍스트 마커를 사용 하 여](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [레거시 API를 사용 하 여 편집기 컨트롤 및 메뉴를 사용자 지정](../extensibility/customizing-editor-controls-and-menus-by-using-the-legacy-api.md)