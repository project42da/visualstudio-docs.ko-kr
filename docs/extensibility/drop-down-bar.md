---
title: 드롭다운 표시줄 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - drop-down bar
ms.assetid: 4bb621bd-72f5-43d5-916f-9f66617da049
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0cf01e8a416407c570076812bf18aa6b21c21583
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="drop-down-bar"></a>드롭다운 표시줄
드롭다운 표시줄 코드 창 위쪽에 제공 하며 드롭 다운 목록 두 개를 포함 합니다.  
  
## <a name="drop-down-bar-interfaces"></a>드롭다운 표시줄 인터페이스  
 [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)], 드롭 다운 표시줄에 대 한 목록을 포함 하는 예를 들어 [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] 항목 및 [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] 항목 멤버 함수를 다음 그림에 나와 있는 것 처럼 합니다.  
  
 ![Drop&#45;막대를 아래로](../extensibility/media/vsdropdown_bar.gif "vsDropdown_bar")  
드롭다운 표시줄  
  
 드롭다운 표시줄을 구현할 때 가지 가장 중요 네 가지 인터페이스가 있습니다.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarClient>  
  
     드롭다운 표시줄의 콘텐츠를 삽입 하려면이 인터페이스를 구현 합니다. 일반 텍스트 또는 고급 텍스트 각 드롭 다운 조합이 포함 될 수 있습니다 (굵게, 기울임꼴 또는 밑줄,), 창 텍스트 글꼴 색 지정 또는 회색된 글꼴 색 지정, 가질 수 있습니다 및 드롭다운 목록 항목 옆에 작은 비트맵을 선택적으로 제공할 수 있습니다. 비슷합니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> 인터페이스, 비트맵 이미지는 이미지 목록에 제공 됩니다. 각 드롭 다운 조합 다른 이미지 목록; 있을 수 있습니다. 그러나 각각 이미지 목록의 이미지의 높이 같게 만들기를 포함 해야 합니다. 또한를 사용 하 여 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarClient.GetComboTipText%2A> 메서드를 각 조합에 대해 도구 설명을 제공할 수 있습니다.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager>  
  
     만들기 또는 삭제는 코드 창에 대 한 드롭다운 표시줄이이 인터페이스를 호출 합니다. 이 인터페이스 드롭다운 막대로 이미에 연결 되었는지 여부는 코드 창 호출 하 여 확인을 사용할 수도 있습니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager.GetDropdownBar%2A> 메서드. 호출 <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> 에 대 한 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager> 에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>합니다.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBar>  
  
     드롭다운 표시줄와 직접 통신 하기 위해이 인터페이스를 호출 합니다. 이 인터페이스를 사용 하 여 강제로 새로 고침 드롭 다운의 내용을 막대 또는 목록 상자에서 선택 항목을 변경 합니다.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManagerEvents>  
  
     등록 한 경우는 `ShowDropdownBarOption` 언어 서비스 레지스트리 키에 다음 코드 창 관리자 모니터링 해야이 이벤트를 드롭 다운 표시줄을 표시 해야 하는지 여부에 대 한 사용자 기본 설정으로 동기화 합니다. 언어 서비스 키의이 옵션을 등록 하지 않은 경우에 드롭 다운 표시줄을 표시 하거나 숨기려면 옵션은 사용할 수는 **옵션** 메뉴.  
  
## <a name="attaching-a-drop-down-bar-to-a-code-window"></a>코드 창에 연결 하는 드롭다운 표시줄  
 드롭다운 목록에 연결 해야 언어 서비스를 연결 하려면 드롭다운 막대로 코드 창으로 만들어질 때 막대는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.AddAdornments%2A> 메서드를 호출 합니다. 호출 하는 경우는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager.GetDropdownBar%2A> 메서드 드롭다운 막대로 존재 다음 호출 되어 있지 않습니다 나타냅니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager.AddDropdownBar%2A>합니다. 에 액세스 하려면는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager> 인터페이스를 호출 <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> 에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> 포인터를 반환 하면 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> 구현이 연결 되었습니다.  
  
## <a name="see-also"></a>참고 항목  
 [레거시 API를 사용 하 여 코드 창을 사용자 지정](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)   
 [레거시 언어 서비스의 탐색 모음 지원](../extensibility/internals/support-for-the-navigation-bar-in-a-legacy-language-service.md)