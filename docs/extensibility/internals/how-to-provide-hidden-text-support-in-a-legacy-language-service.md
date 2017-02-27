---
title: "방법: 레거시 언어 서비스에 대 한 숨겨진된 텍스트 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "숨겨진 텍스트를 지 원하는"
  - "편집기 [Visual Studio SDK], 숨겨진 텍스트"
  - "숨겨진된 텍스트 영역을 구현 하는 언어 서비스"
ms.assetid: 1c1dce9f-bbe2-4fc3-a736-5f78a237f4cc
caps.latest.revision: 21
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 21
---
# 방법: 레거시 언어 서비스에 대 한 숨겨진된 텍스트 지원
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

숨겨진된 텍스트 영역의 개요 영역을 만들 수 있습니다.  숨겨진된 텍스트 영역 클라이언트 제어 또는 편집기 제어할 수 및 텍스트 영역을 완전히 숨길 수 있습니다.  편집기 숨겨진된 영역에 가로 선으로 표시 됩니다.  이러한 예는 스크립트 전용 보기 HTML 편집기에서입니다.  
  
## 절차  
  
#### 숨겨진된 텍스트 영역 구현  
  
1.  Call `QueryService` for <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>.  
  
     이에 대 한 포인터를 반환 합니다. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager>.  
  
2.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.GetHiddenTextSession%2A>, passing에서 주어진된 텍스트 버퍼에 대 한 포인터입니다.  숨겨진된 텍스트 세션이 이미에 대 한 버퍼가 있는지 여부를 결정 합니다.  
  
3.  이미, 다음 하나 하 고 기존에 대 한 포인터를 만들 필요가 없습니다 경우 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> 개체를 반환 합니다.  이 포인터를 사용 하 여 열거 하 고 숨겨진된 텍스트 영역을 만들 수 있습니다.  그렇지 않으면 호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.CreateHiddenTextSession%2A> 숨겨진된 텍스트는 버퍼에 대 한 세션을 만들 수 있습니다.  
  
     에 대 한 포인터를 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> 개체를 반환 합니다.  
  
    > [!NOTE]
    >  호출 하면 `CreateHiddenTextSession`, 숨겨진된 텍스트 클라이언트를 지정할 수 있습니다 \(즉, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextClient>\).  클라이언트 숨겨진된 텍스트 숨겨진된 텍스트 또는 개요 확장 또는 사용자가 축소 때 알립니다.  
  
4.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession.AddHiddenRegions%2A> 중 하나를 추가 하거나 더 새로운 영역에서 다음 정보를 지정 하 한 번 개요는 `reHidReg` \(<xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion>\) 매개 변수:  
  
    1.  값을 지정 `hrtConcealed` 에 `iType` 소속은 <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> 구조 개요 영역 보다는 숨겨진된 영역을 만드는 경우를 나타낼 수 있습니다.  
  
        > [!NOTE]
        >  편집기 숨겨진된 영역이 숨겨져 있으면 숨겨진된 영역이 자신의 현재 상태를 나타내기 위해 주위를 자동으로 표시 됩니다.  
  
    2.  지역 클라이언트 제어 또는 편집기 제어에서 지정은 `dwBehavior` 의 멤버는 <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> 구조.  스마트 개요 구현을 편집기 및 클라이언트 제어 개요와 숨겨진된 된 텍스트 영역을 포함할 수 있습니다.