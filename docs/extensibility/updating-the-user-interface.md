---
title: "사용자 인터페이스 업데이트 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "사용자 인터페이스를 업데이트"
  - "UI 업데이트 명령"
ms.assetid: 376e2f56-e7bf-4e62-89f5-3dada84a404b
caps.latest.revision: 41
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 41
---
# 사용자 인터페이스 업데이트
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

명령의 구현한 후에 새 명령의 상태와 사용자 인터페이스를 업데이트 하는 코드를 추가할 수 있습니다.  
  
 일반적인 Win32 응용 프로그램에서 명령 집합 지속적으로 폴링할 수 및 해당 사용자를 볼 때 개별 명령의 상태를 조정할 수 있습니다. 그러나 때문에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 셸 개수에 제한 없이 Vspackage 호스팅할 수, 광범위 한 폴링 응답성, 특히 관리 코드와 COM. interop 어셈블리에서 폴링 저하 될 수 있습니다  
  
### UI 업데이트  
  
1.  다음 단계 중 하나를 수행합니다.  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.UpdateCommandUI%2A> 메서드를 호출합니다.  
  
         <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> 에서 인터페이스를 가져올 수는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> 서비스를 다음과 같이 합니다.  
  
        ```c#  
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
  
         하는 경우의 매개 변수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.UpdateCommandUI%2A> 0이 아닌 \(`TRUE`\)를 동기적으로, 즉시 업데이트 수행 됩니다. 0을 전달 하는 것이 좋습니다 \(`FALSE`\) 좋은 성능을 유지 하기 위해이 매개 변수입니다. 캐싱을 방지 하려는 경우 적용 된 `DontCache` .vsct 파일에서 명령을 만들 때 플래그입니다. 그럼에도 불구 하 고 플래그를 신중 하 게 사용 또는 성능 저하 될 수 있습니다. 명령 플래그에 대 한 자세한 내용은 참조는 [명령 플래그 요소](../extensibility/command-flag-element.md) 설명서입니다.  
  
    -   창에서 현재 위치 활성화 모델을 사용 하 여 ActiveX 컨트롤을 호스팅하는 Vspackage에서 사용 하 여 더 편리할 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager.UpdateUI%2A> 메서드.<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.UpdateCommandUI%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> 인터페이스 및 <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager.UpdateUI%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager> 인터페이스는 기능적으로 동일 합니다. 둘 다 다시 모든 명령의 상태를 쿼리 하는 환경을 발생 합니다. 일반적으로 업데이트가 즉시 수행 되지 않습니다. 대신 업데이트는 유휴 시간까지 지연 됩니다. 셸 좋은 성능을 유지 하기 위해 명령 상태를 캐시 합니다. 캐싱을 방지 하려는 경우 적용 된 `DontCache` .vsct 파일에서 명령을 만들 때 플래그입니다. 그럼에도 불구 하 고 사용 하 여 플래그를 신중 하 게 되므로 성능이 저하 될 수 있습니다.  
  
         공지를 가져올 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager> 를 호출 하 여 인터페이스는 `QueryInterface` 메서드를는 <xref:Microsoft.VisualStudio.Shell.Interop.IOleComponentUIManager> 또는 개체에서 인터페이스를 가져오는 <xref:Microsoft.VisualStudio.Shell.Interop.SOleComponentUIManager> 서비스입니다.  
  
## 참고 항목  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [구현](../extensibility/internals/command-implementation.md)