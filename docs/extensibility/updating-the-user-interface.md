---
title: "사용자 인터페이스를 업데이트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user interfaces, updating
- commands, updating UI
ms.assetid: 376e2f56-e7bf-4e62-89f5-3dada84a404b
caps.latest.revision: "41"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 02bf66cba145b1d5fdaea899ca3af4ca2bcefbe1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="updating-the-user-interface"></a>사용자 인터페이스 업데이트
명령을 구현 하 고 나면 새 명령의 상태와 사용자 인터페이스를 업데이트 하는 코드를 추가할 수 있습니다.  
  
 일반적인 Win32 응용 프로그램 명령 집합을 지속적으로 폴링할 수 및 해당 사용자를 볼 때의 개별 명령 상태를 조정할 수 있습니다. 그러나 때문에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 셸 개수에 제한 없이 Vspackage 호스팅할 수 있습니다, 광범위 한 폴링 응답성, 관리 코드와 COM. interop 어셈블리에서 폴링 특히 저하 될 수 있습니다  
  
### <a name="to-update-the-ui"></a>UI를 업데이트 하려면  
  
1.  다음 단계 중 하나를 수행합니다.  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.UpdateCommandUI%2A> 메서드를 호출합니다.  
  
         <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> 인터페이스에서 얻을 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> 서비스를 다음과 같이 합니다.  
  
        ```csharp  
        void UpdateUI(Microsoft.VisualStudio.Shell.ServiceProvider sp)  
        {  
            IVsUIShell vsShell = (IVsUIShell)sp.GetService(typeof(IVsUIShell));  
            if (vsShell != null)  
            {  
                int hr = vsShell.UpdateCommandUI(0);  
                Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(hr);  
            }  
        }  
  
        ```  
  
         하는 경우의 매개 변수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.UpdateCommandUI%2A> 0이 아닌 (`TRUE`)를 동기적으로 처리 하 고 즉시 업데이트 수행 됩니다. 0을 전달 하는 것이 좋습니다 (`FALSE`)에 대 한 좋은 성능을 유지할 수 있도록이 매개 변수입니다. 캐싱 하지 않으려는 경우 적용 된 `DontCache` .vsct 파일에서 명령을 만들 때 플래그입니다. 그럼에도 불구 하 고 신중 하 게 플래그를 사용 하거나 성능이 떨어질 수 있습니다. 명령 플래그에 대 한 자세한 내용은 참조는 [명령 플래그 요소](../extensibility/command-flag-element.md) 설명서입니다.  
  
    -   창에서 바로 활성화 모델을 사용 하 여 ActiveX 컨트롤을 호스트 하는 vspackage에서 사용 하는 편리한 방법을 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager.UpdateUI%2A> 메서드. <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.UpdateCommandUI%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> 인터페이스 및 <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager.UpdateUI%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager> 인터페이스는 기능적으로 동일 합니다. 둘 다 인해 환경 다시 모든 명령의 상태를 쿼리 합니다. 일반적으로 업데이트가 즉시 수행 되지 않습니다. 대신, 업데이트는 유휴 시간까지 지연 됩니다. 셸 좋은 성능을 유지할 수 있도록 명령 상태를 캐시 합니다. 캐싱 하지 않으려는 경우 적용 된 `DontCache` .vsct 파일에서 명령을 만들 때 플래그입니다. 그럼에도 불구 하 고 사용할 플래그 주의 성능이 저하 될 수 있습니다.  
  
         공지를 가져올 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager> 호출 하 여 인터페이스는 `QueryInterface` 메서드를는 <xref:Microsoft.VisualStudio.Shell.Interop.IOleComponentUIManager> 개체 또는 여는 인터페이스를 가져오기는 <xref:Microsoft.VisualStudio.Shell.Interop.SOleComponentUIManager> 서비스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [구현](../extensibility/internals/command-implementation.md)