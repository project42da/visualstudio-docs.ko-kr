---
title: "언어 서비스의 지원 개요를 제공 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], outlining support
- language services, supporting outlining
- outlining, supporting
ms.assetid: df759e89-8193-418c-8038-6626304d387b
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d5bc147592bfc36247c35f23ac2885055d096af3
ms.openlocfilehash: fc502e4430a49284cffe14386249999d82085f1c
ms.lasthandoff: 02/22/2017

---
# <a name="how-to-provide-expanded-outlining-support-in-a-legacy-language-service"></a>방법: 레거시 언어 서비스의 확장 된 개요 지원 제공
두 가지 옵션이 있습니다 지원할 언어에 대 한 개요 지원을 확장 하는 데는 **정의 부분만** 명령입니다. 편집기 제어 개요 영역을 추가 하 고 클라이언트에서 제어 되는 개요 영역 수 있습니다.  
  
## <a name="adding-editor-controlled-outline-regions"></a>편집기 제어 개요 영역 추가  
 축소 된 상태 개요 영역을 만들고 지역 확장 되었는지 여부를 처리 하는 편집기를 사용 하려면이 방법을 사용 하 고 등입니다. 지원 개요를 제공 하기 위한 두 가지 옵션을이 옵션은 가장 약한 있습니다. 이 옵션에 대 한 텍스트 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A>.</xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> 를 사용 하 여 지정 된 기간 동안 새 개요 영역을 만들 이 영역을 만든 후 해당 동작을 제어 하는 편집기에서. 다음 절차를 사용 하 여 편집기 제어 개요 영역을 구현 합니다.  
  
#### <a name="to-implement-an-editor-controlled-outline-region"></a>한 편집기 제어 개요 영역을 구현 하려면  
  
1.  호출 `QueryService` 에 대 한<xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager></xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>  
  
     이 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager>.</xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager> 에 대 한 포인터를 반환  
  
2.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.GetHiddenTextSession%2A>, 지정 된 텍스트 버퍼에 대 한 포인터를 전달 합니다.</xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.GetHiddenTextSession%2A> 에 대 한 포인터를 반환 하는이 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession>버퍼에 대 한 개체입니다.</xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession>  
  
3.  <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession>.</xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession> 에 대 한 포인터에 대 한</xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> </xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> 호출  
  
4.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A>을 추가 하거나 더 새로운 한 번에 영역을 설명 합니다.</xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A>  
  
     이 메서드를 사용 하면 개요, 기존 개요 영역을 제거 하거나 보존 여부 및 개요 영역 확장 여부 또는 기본적으로 축소 하는 텍스트의 범위를 지정할 수 있습니다.  
  
## <a name="adding-client-controlled-outline-regions"></a>클라이언트에서 제어 되는 개요 영역 추가  
 사용에서 사용 하는이 방법은 클라이언트 제어 (또는 스마트) 구현 개요 같은 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 및 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 언어 서비스입니다. 자체 개요를 관리 하는 언어 서비스는 유효 하지 않게 될 때 기존 개요 영역을 제거 하 고 필요에 따라 새 개요 영역을 만들를 텍스트 버퍼의 내용이 모니터링 합니다.  
  
#### <a name="to-implement-a-client-controlled-outline-region"></a>클라이언트에서 제어 되 개요 영역을 구현 하려면  
  
1.  호출 `QueryService` <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>.</xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager> 이 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager>.</xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager> 에 대 한 포인터를 반환  
  
2.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.GetHiddenTextSession%2A>, 지정 된 텍스트 버퍼에 대 한 포인터를 전달 합니다.</xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.GetHiddenTextSession%2A> 버퍼에 대 한 숨겨진된 텍스트 세션이 이미 있는지 여부를 결정 합니다.  
  
3.  텍스트 세션이 이미 존재 하는 경우, 한 기존에 대 한 포인터를 만들 필요가 없습니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession>개체가 반환 됩니다.</xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> 이 포인터를 사용 하 여 열거 하 고 개요 영역을 만듭니다. 그렇지 않으면 호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.CreateHiddenTextSession%2A>버퍼에 대 한 숨겨진된 텍스트 세션을 만듭니다.</xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.CreateHiddenTextSession%2A> 에 대 한 포인터는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession>개체가 반환 됩니다.</xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession>  
  
    > [!NOTE]
    >  호출 하는 경우 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.CreateHiddenTextSession%2A>, 숨겨진된 텍스트 클라이언트를 지정할 수 있습니다 (즉, 한 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextClient>개체).</xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextClient> </xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.CreateHiddenTextSession%2A> 이 클라이언트 알리는 경우 숨겨진된 텍스트 또는 개요 영역 확장 또는 사용자가 축소 합니다.  
  
4.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession.AddHiddenRegions%2A>구조) 매개 변수: 값을 지정 <xref:Microsoft.VisualStudio.TextManager.Interop.HIDDEN_REGION_TYPE>에 `iType` 의 멤버는 <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion>숨겨진된 영역 보다는 한 개요 영역을 만드는 것을 나타내기 위해 구조.</xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> </xref:Microsoft.VisualStudio.TextManager.Interop.HIDDEN_REGION_TYPE> </xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession.AddHiddenRegions%2A> 지역에서 편집기 제어 또는 클라이언트 제어 인지 여부를 지정 된 `dwBehavior` 의 멤버는 <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion>구조.</xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> 스마트 개요 구현 다양 한 편집기 및 클라이언트 제어 개요 영역을 포함할 수 있습니다. 개요 영역 축소 되는 경우, 같은 "..."에 표시 되는 배너 텍스트를 지정 된 `pszBanner` 의 멤버는 <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion>구조.</xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> 숨겨진된 영역에 대 한 편집기의 기본 배너 텍스트는 "..."입니다.
