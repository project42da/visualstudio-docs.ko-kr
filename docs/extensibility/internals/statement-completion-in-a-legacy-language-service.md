---
title: "레거시 언어 서비스에서 문 완성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- statement completion
- language services, statement completion
ms.assetid: 617439dc-3f0e-4e5f-b346-3e4e7fcf3c1b
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c694295c3456accc8d2c1cd3b0a1ec20f59343c3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="statement-completion-in-a-legacy-language-service"></a>레거시 언어 서비스에서 문 완성
문 완성은 언어 서비스는 기준인 언어 키워드 또는 코어 편집기에 입력 시작 요소를 완료 하는 사용자가 사용 하면 프로세스입니다. 이 항목에서는 문 완성이 작동 방식 및 언어 서비스에서 구현 하는 방법을 설명 합니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 된 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 최신 방법입니다. 문 완성 기능을 구현 하는 새로운 방법에 대해 자세히 알아보려면 참조 [연습: 문 완성 표시](../../extensibility/walkthrough-displaying-statement-completion.md)합니다.  
  
> [!NOTE]
>  편집기를 사용 하 여 새 API 가능한 한 빨리 시작 하는 것이 좋습니다. 언어 서비스의 성능이 향상 되 고 새 편집기 기능을 이용할 수 있도록 합니다.  
  
## <a name="implementing-statement-completion"></a>문 완성 기능을 구현합니다.  
 핵심 편집기에서 문 완성을 대화형으로 사용 하면 보다 쉽게 고 신속 하 게 코드를 작성 하는 특별 한 UI 활성화 합니다. 문 완성을 표시 하 여 관련 개체 또는 클래스는 필요할 때 특정 요소를 사용 하지 도움말 참조 항목에서 조회할 필요 하거나이 방지 하는 데 도움이 됩니다.  
  
 문 완성 기능을 구현 하려면 해당 언어 구문 분석할 수 있는 트리거 문 완성 있어야 합니다. 예를 들어 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 점 (.) 연산자를 사용 하는 동안 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 화살표를 사용 하 여 (->) 연산자. 언어 서비스는 둘 이상의 트리거를 사용 하 여 문 완성을 시작할 수 있습니다. 명령 필터에이 트리거 프로그래밍 됩니다.  
  
## <a name="command-filters-and-triggers"></a>명령 파일 및 트리거  
 명령을 필터 일치를 트리거 또는 트리거를 가로챕니다. 명령 필터 보기를 추가 하려면 구현는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스를 호출 하 여 보기에 연결 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> 메서드. 동일한 명령 필터를 사용할 수 있습니다 (<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>) 언어 서비스 문 완성, 오류 표식 메서드 팁 등의 모든 측면에 대 한 합니다. 자세한 내용은 참조 [레거시 언어 서비스 명령 가로채](../../extensibility/internals/intercepting-legacy-language-service-commands.md)합니다.  
  
 트리거를 편집기에 입력 된 경우-텍스트 버퍼 특히-언어 서비스가 다음 호출는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> 메서드. 이렇게 하면 편집기에서 문 완성 후보 사용자가 선택할 수 있도록 UI를 표시 합니다. 이 메서드를 구현 해야 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.UpdateCompletionFlags> 매개 변수로 플래그입니다. 완료 항목 목록이 스크롤 목록 상자에 나타납니다. 사용자가 입력을 계속, 목록 상자에서 선택한 입력 한 가장 최근의 자로 가까운 반영 하도록 업데이트 됩니다. 핵심 편집기의 문 완성, UI를 구현 하지만 언어 서비스를 구현 해야 합니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> 문에 대 한 후보 완성 항목의 집합을 정의 하는 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [레거시 언어 서비스 명령 가로채기](../../extensibility/internals/intercepting-legacy-language-service-commands.md)