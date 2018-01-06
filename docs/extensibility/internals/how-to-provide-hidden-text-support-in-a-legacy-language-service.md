---
title: "방법: 레거시 언어 서비스에 대 한 숨겨진된 텍스트 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- hidden text, supporting
- editors [Visual Studio SDK], hidden text
- language services, implementing hidden text regions
ms.assetid: 1c1dce9f-bbe2-4fc3-a736-5f78a237f4cc
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 664ab99af45e8c449247c5515184293ecb1a469f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-provide-hidden-text-support-in-a-legacy-language-service"></a>방법: 레거시 언어 서비스에 대 한 숨겨진된 텍스트 지원
개요 영역 뿐만 아니라 숨겨진된 텍스트 영역을 만들 수 있습니다. 숨겨진된 텍스트 영역 수도 있고 클라이언트 제어 편집기 제어 텍스트 영역을 완전히 숨기려면 하는 데 사용 됩니다. 편집기는 가로선으로 숨겨진된 영역을 표시합니다. 이러한 예는 HTML 편집기에서 스크립트 전용 뷰입니다.  
  
## <a name="procedure"></a>프로시저  
  
#### <a name="to-implement-a-hidden-text-region"></a>숨겨진된 텍스트 영역을 구현 하려면  
  
1.  호출 `QueryService` 에 대 한 <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>합니다.  
  
     에 대 한 포인터를 반환 합니다. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager>합니다.  
  
2.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.GetHiddenTextSession%2A>, 지정 된 텍스트 버퍼에 대 한 포인터를 전달 합니다. 버퍼에 대 한 숨겨진된 텍스트 세션이 이미 있는지 여부를 결정 합니다.  
  
3.  이미 있는 경우와 기존에 대 한 포인터를 만들 필요가 없습니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> 개체가 반환 됩니다. 이 포인터를 사용 하 여 열거 하 고 숨겨진된 텍스트 영역을 만듭니다. 그렇지 않으면 호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.CreateHiddenTextSession%2A> 버퍼에 대 한 숨겨진된 텍스트 세션을 만들 수 있습니다.  
  
     에 대 한 포인터는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> 개체가 반환 됩니다.  
  
    > [!NOTE]
    >  호출 하는 경우 `CreateHiddenTextSession`, 숨겨진된 텍스트 클라이언트를 지정할 수 있습니다 (즉, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextClient>). 숨겨진된 텍스트 클라이언트 숨겨진된 텍스트 또는 개요 확장 또는 사용자가을 축소 하는 경우이 알려 줍니다.  
  
4.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession.AddHiddenRegions%2A> 을 추가 하거나 더 새로운 개요 영역 한 번에에서 다음 정보를 지정 하는 `reHidReg` (<xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion>) 매개 변수:  
  
    1.  값을 지정 `hrtConcealed` 에 `iType` 의 멤버는 <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> 구조 한 개요 영역 보다는 숨겨진된 영역을 만드는 것을 나타냅니다.  
  
        > [!NOTE]
        >  숨겨진된 영역을 숨기면 편집기에 자동으로 현재 상태를 나타내기 위해 숨겨진된 영역 주위에 선을 표시 됩니다.  
  
    2.  지역에서 편집기 제어 또는 클라이언트 제어 인지 지정는 `dwBehavior` 의 멤버는 <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> 구조입니다. 스마트 개요 구현에는 다양 한 편집기 및 클라이언트에서 제어 되는 개요 및 숨겨진된 텍스트 영역 포함 될 수 있습니다.