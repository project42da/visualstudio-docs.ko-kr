---
title: "언어 서비스에 대 한 지원을 명시 제공 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], outlining support
- language services, supporting outlining
- outlining, supporting
ms.assetid: df759e89-8193-418c-8038-6626304d387b
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1133166560fa371bbb5a2b008175034d48a2a7b5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-provide-expanded-outlining-support-in-a-legacy-language-service"></a>방법: 레거시 언어 서비스에서 개요를 지 원하는 확장
해당 언어를 지원할에 대 한 개요 지원을 확장 하기 위한 다음과 같은 **정의 부분만** 명령입니다. 편집기 제어 개요 영역을 추가 하 고 클라이언트에서 제어 되는 개요 영역 수 있습니다.  
  
## <a name="adding-editor-controlled-outline-regions"></a>편집기 제어 개요 영역을 추가합니다.  
 축소 된 상태를 한 개요 영역을 만들고 지역 확장 되었는지 여부를 처리 하 여 편집기를 통해 이러한 접근 방식을 사용 하 고 등입니다. 이 옵션은 지원 개요를 제공 하는 데 두 옵션 중 가장 약한 있습니다. 이 옵션을 사용 하 여 텍스트의 지정 된 기간 동안 새 개요 영역을 만들 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A>합니다. 이 영역을 만든 후 해당 동작은 편집기에 의해 제어 됩니다. 다음 절차를 사용 하 여 편집기 제어 개요 영역을 구현 합니다.  
  
#### <a name="to-implement-an-editor-controlled-outline-region"></a>한 편집기 제어 개요 영역을 구현 하려면  
  
1.  호출 `QueryService` 에 대 한<xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>  
  
     에 대 한 포인터를 반환 합니다. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager>합니다.  
  
2.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.GetHiddenTextSession%2A>, 지정 된 텍스트 버퍼에 대 한 포인터를 전달 합니다. 에 대 한 포인터를 반환 합니다.는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> 버퍼에 대 한 개체입니다.  
  
3.  호출 <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> 에 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> 에 대 한 포인터에 대 한 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession>합니다.  
  
4.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> 을 추가 하거나 더 새로운 한 번에 영역을 설명 합니다.  
  
     이 메서드를 사용 하면 개요, 기존 개요 영역 제거 되었거나 유지 여부 및 여부 개요 영역 확장 또는 기본적으로 축소 하는 텍스트 범위를 지정할 수 있습니다.  
  
## <a name="adding-client-controlled-outline-regions"></a>클라이언트에서 제어 되는 개요 영역을 추가합니다.  
 이 방법은 클라이언트 제어 (또는 스마트) 구현 개요에서 사용 하는 등의 사용은 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 및 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 언어 서비스입니다. 유효 하지 않게 될 때 기존 개요 영역을 제거 하 고 필요에 따라 새 개요 영역을 만들 수 개요 자체를 관리 하는 언어 서비스 텍스트 버퍼 콘텐츠를 모니터링 합니다.  
  
#### <a name="to-implement-a-client-controlled-outline-region"></a>클라이언트에서 제어 되 개요 영역을 구현 하려면  
  
1.  호출 `QueryService` 에 대 한 <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>합니다. 에 대 한 포인터를 반환 합니다. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager>합니다.  
  
2.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.GetHiddenTextSession%2A>, 지정 된 텍스트 버퍼에 대 한 포인터를 전달 합니다. 버퍼에 대 한 숨겨진된 텍스트 세션이 이미 있는지 여부를 결정 합니다.  
  
3.  텍스트 세션이 이미 있는 경우 하나, 및 기존에 대 한 포인터를 만들 필요가 없습니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> 개체가 반환 됩니다. 이 포인터를 사용 하 여 열거 하 고 개요 영역을 만듭니다. 그렇지 않으면 호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.CreateHiddenTextSession%2A> 버퍼에 대 한 숨겨진된 텍스트 세션을 만들 수 있습니다. 에 대 한 포인터는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> 개체가 반환 됩니다.  
  
    > [!NOTE]
    >  호출 하는 경우 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.CreateHiddenTextSession%2A>, 숨겨진된 텍스트 클라이언트를 지정할 수 있습니다 (즉, 한 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextClient> 개체). 이 클라이언트 알림을 표시 하면 숨겨진된 텍스트 또는 개요 영역 확장 또는 사용자가을 축소 합니다.  
  
4.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession.AddHiddenRegions%2A> 구조) 매개 변수: 값을 지정 <xref:Microsoft.VisualStudio.TextManager.Interop.HIDDEN_REGION_TYPE> 에 `iType` 의 멤버는 <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> 구조는 숨겨진된 영역 보다는 한 개요 영역을 만드는 것을 나타냅니다. 지역에서 편집기 제어 또는 클라이언트 제어 인지 지정는 `dwBehavior` 의 멤버는 <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> 구조입니다. 스마트 개요 구현 다양 한 편집기 및 클라이언트에서 제어 되는 개요 영역을 포함할 수 있습니다. 개요 영역을 축소 "..." 등의 경우 표시 되는 배너 텍스트를 지정 된 `pszBanner` 의 멤버는 <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> 구조입니다. 숨겨진된 영역에 대 한 편집기의 기본 배너 텍스트는 "..."입니다.