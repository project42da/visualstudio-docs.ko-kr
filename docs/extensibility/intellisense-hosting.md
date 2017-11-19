---
title: "IntelliSense 호스팅 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - IntelliSense hosting
ms.assetid: 20c61f8a-d32d-47e2-9c67-bf721e2cbead
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 850e4b2ef6d455bb141827fa125c4c7c6860b652
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="intellisense-hosting"></a>IntelliSense 호스팅
Visual Studio IntelliSense 호스팅 수 있습니다. Visual Studio 텍스트 편집기에서 호스트 되지 않는 코드에 대 한 IntelliSense를 제공 하면 IntellSense 사용 하면 호스팅.  
  
## <a name="intellisense-hosting-usage"></a>IntelliSense 호스팅 사용  
 Visual Studio에서 완료 집합과 텍스트 버퍼에 대 한 액세스 권한이 있는 모든 코드를 가져올 수 IntelliSense windows 어디에서 나 사용자 인터페이스 (UI)에 있습니다. 이 몇 가지 예제 시나리오에서 완성 되는 **조사식** 창 또는 중단점 속성 창의 조건 필드입니다.  
  
### <a name="implementation-interfaces"></a>인터페이스 구현  
  
#### <a name="ivsintellisensehost"></a>IVsIntellisenseHost  
 IntelliSense 팝업 창을 호스트 하는 UI 구성 요소를 지원 해야 합니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 인터페이스입니다. 기본 핵심 편집기 텍스트 보기에는 주가 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 인터페이스 구현 현재 IntelliSense 기능을 유지 해야 합니다. 대부분의 경우의 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 나타내며의 기능 하위 집합에서 구현 되는 인터페이스는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 인터페이스입니다. IntelliSense UI 처리, 캐럿 및 선택 조작 및 간단한 텍스트 대체 기능 하위 집합에 포함 되어 있습니다. 또한는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 인터페이스를 사용 하면 별도 IntelliSense "subject" 및 "컨텍스트"를 컨텍스트에 대해 사용 되는 텍스트 버퍼에 직접 존재 하지 않는 주제에 대 한 IntelliSense를 제공할 수 있습니다.  
  
#### <a name="ivsintellisensehostgethostflags"></a>IVsIntellisenseHost.GetHostFlags  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 인터페이스 공급자 구현 해야 합니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetHostFlags%2A> 어떤 유형의 IntelliSense 호스트 기능을 확인 하려면 클라이언트를 사용 하는 메서드를 지원 합니다.  
  
 에 정의 된 호스트 플래그 [IntelliSenseHostFlags](../extensibility/intellisensehostflags.md), 아래에 요약 되어 있습니다.  
  
|IntelliSense 호스트 플래그|설명|  
|----------------------------|-----------------|  
|IHF_READONLYCONTEXT|상황에 맞는 버퍼가 있는 플래그 설정 읽기 전용 및 편집 내 에서만 발생 제목 텍스트입니다.|  
|IHF_NOSEPERATESUBJECT|설정 플래그 있는 별도 IntelliSense 제목 없음입니다. 주체에에서 존재 컨텍스트 버퍼와 같은 기존의에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> IntelliSense 시스템입니다.|  
|IHF_SINGLELINESUBJECT|제목 없는 플래그 설정에서 편집 가능 등에서 한 줄 여러 줄의 **조사식** 창.|  
|IHF_FORCECOMMITTOCONTEXT|이 플래그가 설정 된 컨텍스트 버퍼로 업데이트 해야 하는 경우 호스트에는 무시할 컨텍스트 버퍼에 대 한 읽기 전용 플래그 및 계속 하려면는 편집할 수 있습니다.|  
|IHF_OVERTYPE|(제목 또는 컨텍스트)에서 편집 겹쳐쓰기 모드에서 수행 되어야 합니다.|  
  
#### <a name="ivsintellisensehostbeforecompletorcommit-and-ivsintellisensehostaftercompletorcommit"></a>IVsIntellisenseHost.BeforeCompletorCommit 및 IVsIntellisenseHost.AfterCompletorCommit  
 이러한 콜백 메서드로 텍스트 전처리 및 후 처리를 사용 하도록 설정 하려면 커밋된 후 전과 완료 창에 의해 호출 됩니다.  
  
#### <a name="ivsintellisensecompletor"></a>IVsIntellisenseCompletor  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseCompletor> 인터페이스의 통합된 개발 환경 (IDE)에서 사용 되는 표준 완성 창 공동으로 만들 수 있는 버전이 있습니다. 모든 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 인터페이스가 completor 인터페이스를 사용 하 여 IntelliSense를 신속 하 게 구현할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.TextManager.Interop>