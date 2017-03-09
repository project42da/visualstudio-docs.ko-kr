---
title: "사용자 지정 속성 창 제공 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "속성 브라우저, 제공"
  - "속성 창, 고유한 창 제공"
ms.assetid: 408dcdef-8ef9-4644-97d2-f311cd35824f
caps.latest.revision: 12
caps.handback.revision: 12
manager: "douge"
---
# 사용자 지정 속성 창 제공
직접 제공 하는 것이 가능  **속성** 창을 확장 하는 대신 특정된 프로젝트 시스템에 대 한의  **속성** 에서 제공 하는 윈도우는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\).  자신이 창 프레임에 배치 하는 개체를 구현할 때 가장 자주 발생된 하는 시나리오가입니다.  
  
 창 프레임을 배치 합니다. 개체를 구현 하지 않지만 여전히 다른 방법으로 해당 액세스 권한이 이벤트에 여러 가지 방법으로 액세스할 수 있는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> 이 페이지의 마지막 절차에 나열 된 것 처럼 인터페이스.  
  
### 속성 창에서 제공 하  
  
1.  정의 나타내는 GUID를  **속성** 창 구현 합니다.  
  
2.  사용자 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> 구현을 사용은 <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> proffer 서비스를  **속성** 서비스로 Visual Studio 환경 창.  
  
### 속성 창이 호출.  
  
1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane.SetSite%2A> 메서드를 호출합니다.  
  
2.  `QueryService`에 대 한 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx> 에서 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> 전달 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane.SetSite%2A> 메서드.  
  
3.  가져올 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx> 에서 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx> 서비스 합니다.  
  
4.  호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx.OnElementValueChange%2A> 로 설정는 첫 번째 매개 변수 `SEID_PropertyBrowserSID` \(발췌의 <xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID> 열거형\), 및 세 번째 매개 변수를 `varValue`, 폼을 나타내는 GUID 문자열을 나타내는  **속성** 창.  이 한 번만을 처음 만들 때 호출을  **속성** 창 문서 창입니다.  호출 후이  **속성이** 창을 창 프레임에 연결 됩니다.  
  
### 구현 자가 되 면 프레임 창 개체를 가져오려면  
  
-   할 수 있습니다 `QueryService` 에 대 한 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx> 서비스에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> 매개 변수가 `propid` 설정 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>.  
  
-   활성 문서 윈도우를 호출 하 여 얻을 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCurrentSelection%2A> SVsMonitorSelection 서비스를 통해.  매개 변수를 설정 `elementid` 에 `SEID_WindowFrame`, 촬영에서 <xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID> 열거형입니다.  
  
## 참고 항목  
 [속성 확장](../extensibility/internals/extending-properties.md)   
 [속성 창의 필드 및 인터페이스](../extensibility/internals/properties-window-fields-and-interfaces.md)