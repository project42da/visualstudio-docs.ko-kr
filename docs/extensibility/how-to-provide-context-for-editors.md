---
title: "방법: 편집기에 대 한 컨텍스트를 제공 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - provide context
ms.assetid: 12df4d06-df6b-4eaf-a7bf-c83655a0c683
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: d9b89c4e45f8268df55386d321816325fb50174c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-provide-context-for-editors"></a>방법: 편집기에 대 한 컨텍스트를 제공 합니다.
편집기에 대 한는 컨텍스트는 편집기에 포커스가 또는 도구 창으로 포커스 이동 된 바로 전에 포커스가 있던 경우에 활성화 됩니다. 다음을 수행 하 여 편집기에 대 한 컨텍스트를 제공할 수 있습니다.  
  
1.  컨텍스트 모음을 만듭니다.  
  
2.  컨텍스트 모음 선택 요소 식별자 (SEID)에 게시 합니다.  
  
3.  모음에 컨텍스트를 유지 합니다.  
  
 이러한 작업은 다음 절차 포함 되어 있습니다. 컨텍스트를 제공 하는 방법에 대 한 자세한 내용은 참조 **강력한 프로그래밍** 이 항목의 뒷부분에 나오는 합니다.  
  
### <a name="to-create-a-context-bag-for-an-editor-or-a-designer"></a>편집기 또는 디자이너에 대 한 컨텍스트 모음을 만들려면  
  
1.  호출 `QueryService` 에 프로그램 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> 에 대 한 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsMonitorUserContext> 서비스입니다.  
  
     에 대 한 포인터는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorUserContext> 인터페이스를 반환 합니다.  
  
2.  호출 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorUserContext.CreateEmptyContext%2A> 새 컨텍스트 또는 하위 컨텍스트로 모음을 만드는 메서드를 합니다.  
  
     에 대 한 포인터는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext> 인터페이스를 반환 합니다.  
  
3.  호출 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AddAttribute%2A> 메서드 특성, 조회 키워드 또는 F1 키워드를 컨텍스트 또는 하위 컨텍스트로 모음입니다.  
  
4.  하위 컨텍스트로 모음을 만드는 경우 호출 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AddSubcontext%2A> 하위 모음 부모 컨텍스트 모음에 연결 하는 메서드.  
  
5.  호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AdviseUpdate%2A> 알림을 받을 때는 **동적 도움말** 기간은 업데이트 하려고 합니다.  
  
     필요는 **동적 도움말** 창을 호출 하는 편집기를 업데이트할 준비가 되었을 때 하실 수 있으며 지연 업데이트가 수행 될 때까지 컨텍스트를 변경 합니다. 이 작업을 수행 시스템 유휴 시간 있을 때까지 시간이 오래 걸리는 알고리즘 실행을 지연 시킬 수 있기 때문에 성능을 향상 시킬 수 있습니다.  
  
### <a name="to-publish-the-context-bag-to-the-seid"></a>컨텍스트 모음은 SEID를 게시 하려면  
  
1.  호출 `QueryService` 에 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx> 서비스에 대 한 포인터를 반환 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx> 인터페이스입니다.  
  
2.  호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx.OnElementValueChange%2A>, 요소 식별자를 지정 하 (`elementid` 매개 변수)의 전역 수준에 컨텍스트를 전달 하는 있는지 나타내려면 SEID_UserContext의 값입니다.  
  
3.  값, 편집기 또는 디자이너 활성화 되 면 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx> 개체 전역 선택에 전파 됩니다. 세션당 한 번씩이 프로세스를 완료 한 다음 호출 했을 때 만들어진 전역 컨텍스트에 대 한 포인터를 저장 하 고 하기만 하면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx.OnElementValueChange%2A>합니다.  
  
### <a name="to-maintain-the-context-bag"></a>컨텍스트 모음을 유지 하기 위해  
  
1.  구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext> 되도록는 **동적 도움말** 를 업데이트 하기 전에 편집기 또는 디자이너 창을 호출 합니다.  
  
     가 호출 하는 각 컨텍스트 모음에 대 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AdviseUpdate%2A> 컨텍스트 모음 만들고 구현한 후 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate>, IDE 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate.UpdateUserContext%2A> 컨텍스트 모음 업데이트할지 컨텍스트 공급자를 알릴 수 있습니다. 이 호출을 사용 하 여 특성 및 컨텍스트 모음 및 모든 하위 백 키워드를 하기 전에 변경는 **동적 도움말** 창 업데이트가 발생 합니다.  
  
2.  호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.SetDirty%2A> 편집기 또는 디자이너에 새 컨텍스트 있음을 나타내기 위해 컨텍스트 모음에 있습니다.  
  
     경우는 **동적 도움말** 창 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate.UpdateUserContext%2A> 업데이트 하는, 편집기 또는 디자이너 당시에 부모 컨텍스트 모음 및 모든 하위 백 모두에 대해 적절 하 게 컨텍스트를 업데이트할 수 있습니다 하 합니다.  
  
    > [!NOTE]
    >  `SetDirty` 플래그가로 자동으로 설정 되어 `true` 컨텍스트가 추가 되거나 컨텍스트 모음에서 제거 될 때마다 합니다. **동적 도움말** 창만 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate.UpdateUserContext%2A> 컨텍스트 모음에는 경우는 `SetDirty` 플래그가로 설정 되어 `true`합니다. 다시 설정할 `false` 업데이트 후 합니다.  
  
3.  호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AddAttribute%2A> 컨텍스트 활성 컨텍스트 컬렉션에 추가할 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.RemoveAttribute%2A> 컨텍스트를 제거 하려면.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 사용자 고유의 편집기를 작성 하는 경우에 편집기에 대 한 컨텍스트를 제공 하려면이 항목의 절차의 3을 모두 완료 해야 합니다.  
  
> [!NOTE]
>  호출 해야 제대로 편집기 또는 디자이너 창을 활성화 하 고 있는지 명령 라우팅을 업데이트 확인 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> 에 구성 요소에 포커스 창으로 만듭니다.  
  
 SEID은 선택을 기반으로 변경 하는 속성의 컬렉션입니다. SEID 정보는 글로벌 선택을 통해 제공 됩니다. 전역 선택이 의해 트리거되는 이벤트에 연결 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx> 인터페이스를가 있는 모든 항목의 목록을 선택 (현재 편집기, 현재 도구 창, 현재 계층 구조 및 등) 하 고 있습니다.  
  
 편집기 및 디자이너에 대 한 어떤 컨텍스트 될 때마다 변경 될 수 커서 이동가 단어 안에서 것은 비효율적를 지속적으로 컨텍스트 모음을 업데이트 합니다. 보다 효율적인을 편집기 또는 디자이너 창 내에서 이동 하는 커서를 발견 하면 언제 든 지 업데이트를 위해 호출할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.SetDirty%2A>합니다. 이렇게 하면 유휴 시간이 있고 IDE의 상황에 맞는 서비스에 알림을 보냅니다 편집기 또는 디자이너를까지 컨텍스트 변경을 있습니다는 **동적 도움말** 창이 업데이트 됩니다. 이 방식은이 항목의 "컨텍스트 모음 유지 하려면" 절차에서 사용 됩니다.  
  
 편집기 또는 디자이너 내에서 활동에 대 한 컨텍스트를 입력 한 후 사용자가 편집기 또는 디자이너 자체에 대 한 도움말을 볼 수 있도록 특정 F1 키워드를 제공 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx.OnElementValueChange%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AddAttribute%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AdviseUpdate%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.RemoveAttribute%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.SetDirty%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate.UpdateUserContext%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx>