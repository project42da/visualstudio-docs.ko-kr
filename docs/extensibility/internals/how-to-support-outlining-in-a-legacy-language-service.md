---
title: "방법: 레거시 언어 서비스의 개요 기능을 지원 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], collapse to definitions command
- language services, supporting Collapse to Definitions command
- hidden text, Collapse to Definitions command
ms.assetid: bb6e74c3-93e4-4ef7-afc7-1c9b342f083b
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e08ca6d5a670bb2c1a0f0073920c753add50322c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-support-outlining-in-a-legacy-language-service"></a>방법: 레거시 언어 서비스의 개요 기능을 지원 합니다.
개요 확장 또는 텍스트의 다른 영역을 축소 하는 데 사용 됩니다. 사용 되는 방식으로 개요 표시 다른 언어에서 다르게 정의할 수 있습니다. 자세한 내용은 [개요](../../ide/outlining.md)를 참조하세요.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 된 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 최신 방법입니다. 개요 기능을 구현 하는 새로운 방법에 대해 자세히 알아보려면 참조 [연습: 개요](../../extensibility/walkthrough-outlining.md)합니다.  
  
> [!NOTE]
>  편집기를 사용 하 여 새 API 가능한 한 빨리 시작 하는 것이 좋습니다. 언어 서비스의 성능이 향상 되 고 새 편집기 기능을 이용할 수 있도록 합니다.  
  
 다음 언어 서비스에 대해이 명령을 지 원하는 방법을 보여 줍니다.  
  
### <a name="to-support-outlining"></a>개요 기능을 지원 하기 위해  
  
1.  구현 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningCapableLanguage> 언어 서비스 개체에 있습니다.  
  
2.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> 새 개요 영역을 추가 하려면 현재 개요 세션 개체에 있습니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 사용자가 선택할 때 **축소 하려면 정의** 에 **개요** 메뉴, IDE 호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningCapableLanguage.CollapseToDefinitions%2A> 언어 서비스에서 합니다.  
  
 이 메서드는 IDE에서 전달 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> 포인터 (텍스트 버퍼에 대 한 포인터) 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession> (개요 현재 세션에 포인터).  
  
 호출할 수 있습니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> 에 이러한 영역을 지정 하 여 여러 개의 개요 영역에 대 한 메서드는 `rgOutlnReg` 매개 변수입니다. `rgOutlnReg` 매개 변수는 한 <xref:Microsoft.VisualStudio.TextManager.Interop.NewOutlineRegion> 구조입니다. 이 프로세스에 숨겨진된 영역 특정 지역 확장 또는 축소 여부 등의 다른 특성을 지정할 수 있습니다.  
  
> [!NOTE]
>  줄 바꿈 문자 숨기기에 대 한 주의 해야 합니다. 숨겨진된 텍스트 확장 되어야 첫 번째 줄의 시작 부분부터 마지막 마지막 줄 바꿈 문자에 표시 된 채로 섹션에는 마지막 줄의 문자입니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 레거시 언어 서비스에 대 한 숨겨진된 텍스트 지원](../../extensibility/internals/how-to-provide-hidden-text-support-in-a-legacy-language-service.md)   
 [방법: 레거시 언어 서비스에서 확장 개요 표시 지원 제공](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)