---
title: "드롭다운 표시줄 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK], 레거시 드롭다운 표시줄"
ms.assetid: 4bb621bd-72f5-43d5-916f-9f66617da049
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 드롭다운 표시줄
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

드롭다운 표시줄로 위쪽에 코드 창이 제공 되며 두 개의 드롭다운 목록이 포함 되어 있습니다.  
  
## 드롭다운 도구 모음 인터페이스  
 [!INCLUDE[vcprvc](../debugger/includes/vcprvc_md.md)], 예를 들어, 목록에 대 한 드롭다운 도구 모음에 있는 [!INCLUDE[vcprvc](../debugger/includes/vcprvc_md.md)] 항목 및 [!INCLUDE[vcprvc](../debugger/includes/vcprvc_md.md)] 항목 멤버 함수, 다음 그림에 나와 있는 것 처럼.  
  
 ![드롭다운 표시줄](~/extensibility/media/vsdropdown_bar.gif "vsDropdown\_bar")  
드롭다운 도구 모음  
  
 드롭 다운 막대를 구현 하는 경우 기본 중요성의 4 개의 인터페이스입니다.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarClient>  
  
     드롭 다운 막대의 콘텐츠를 삽입 하기 위해이 인터페이스를 구현 합니다.  일반 텍스트 또는 고급 텍스트 각 드롭 다운 조합을 포함할 수 있습니다 \(굵게, 기울임꼴 또는 밑줄\), 창의 텍스트 글꼴 색 이나 색을 회색으로 표시 된 글꼴이 있을 수 있습니다 및 드롭다운 항목 옆에 작은 비트맵을 선택적으로 제공할 수 있습니다.  비슷한에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> 인터페이스를 비트맵 이미지에는 이미지 목록에서 제공 됩니다.  각 드롭 다운 조합 다른 이미지 목록을 만들 수 있습니다. 그러나 각 이미지 목록의 이미지 높이를 포함 해야 합니다.  또한, 사용 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarClient.GetComboTipText%2A> 메서드를 제공할 수 있습니다 도구 설명이 각 조합에 대해.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager>  
  
     만들기 또는 드롭 다운 막대 코드 창에 대 한 파괴 하는이 인터페이스를 호출 합니다.  이 인터페이스 드롭 다운 막대 이미 코드 창에 호출 하 여 연결 되어 있는지 여부를 확인 하려면 사용할 수 있는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager.GetDropdownBar%2A> 방법입니다.  Call <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> for <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager> from <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBar>  
  
     드롭 다운 막대와 직접 통신 하는이 인터페이스를 호출 합니다.  이 인터페이스를 사용 하 여 강제로 새로 고침 드롭다운 내용을 막대 또는 목록 상자 중 하나에서 선택 합니다.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManagerEvents>  
  
     등록 한 경우는 `ShowDropdownBarOption` 언어 서비스 레지스트리 키에 다음 드롭다운 표시줄로 표시 되어야 하는지 여부에 대 한 사용자 기본 설정을 동기화 하려면이 이벤트를 코드 창 관리자 모니터링 해야 합니다.  이 옵션을 언어 서비스 키를 등록 하지 않은 경우 아래쪽 표시줄 표시 \/ 숨기기 옵션을 사용할 수 없습니다의  **옵션** 메뉴입니다.  
  
## 코드 창에 드롭다운 도구 모음 첨부  
 만들 때 드롭 다운 막대를 코드 창에 연결 하려면 언어 서비스 드롭다운을 첨부 해야 합니다 바 시는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.AddAdornments%2A> 메서드가 호출 합니다.  호출 하는 경우는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager.GetDropdownBar%2A> 메서드를 나타내는 드롭다운 표시줄로 하지 이미 존재, 다음 호출 합니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager.AddDropdownBar%2A>.  액세스 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager> 인터페이스를 호출 <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> 에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> 포인터가 반환 하는 경우에 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> 구현 된 연결 된.  
  
## 참고 항목  
 [레거시 API를 사용 하 여 코드를 사용자 지정](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)   
 [레거시 언어 서비스에 탐색 모음에 대 한 지원](../extensibility/internals/support-for-the-navigation-bar-in-a-legacy-language-service.md)