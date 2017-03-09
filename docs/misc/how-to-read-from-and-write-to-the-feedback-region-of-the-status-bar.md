---
title: "방법: 상태 표시줄의 피드백 영역에서 읽기 및 피드백 영역에 쓰기 | Microsoft Docs"
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
  - "피드백 영역, 상태 표시줄"
  - "상태 표시줄, 피드백 영역"
  - "상태 표시줄, 개요"
ms.assetid: e639561c-e1e7-4660-b2a2-8bca80f34a29
caps.latest.revision: 12
caps.handback.revision: 12
manager: "douge"
---
# 방법: 상태 표시줄의 피드백 영역에서 읽기 및 피드백 영역에 쓰기
의견 영역에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 텍스트가 상태 표시줄에 표시 됩니다.  설정 및 텍스트를 검색, 정적 텍스트를 표시 고 표시 되는 텍스트를 강조 표시할 수 있습니다.  
  
### Visual Studio 상태 표시줄의 의견 영역을 사용 하려면  
  
1.  인스턴스를 가져오기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar> 인터페이스를 통해 사용할 수 있게 되는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> 서비스 합니다.  
  
2.  호출 하 여 상태 표시줄이 고정 되어 있는지 여부를 확인은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.IsFrozen%2A> 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar> 인스턴스.  
  
3.  의견 영역의 텍스트를 호출 하 여 설정의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.SetText%2A> 메서드 및 전달 하는 텍스트 문자열입니다.  
  
4.  호출 하 여 사용자 의견 영역의 텍스트를 읽을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.GetText%2A> 메서드.  
  
## 예제  
 이 예제에서는 텍스트를 작성 한 의견 영역에서 텍스트를 읽는 방법을 보여 줍니다.  
  
 [!code-cs[VSSDKFeedbackStatusBar#1](../misc/codesnippet/CSharp/how-to-read-from-and-write-to-the-feedback-region-of-the-status-bar_1.cs)]
 [!code-vb[VSSDKFeedbackStatusBar#1](../misc/codesnippet/VisualBasic/how-to-read-from-and-write-to-the-feedback-region-of-the-status-bar_1.vb)]  
  
 위의 예제에서 코드에서는 다음 작업을 수행합니다.  
  
-   인스턴스를 가져옵니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar> 의 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> 서비스.  
  
-   호출 하 여 상태 표시줄이 고정 되어 있는지 확인을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.IsFrozen%2A> 메서드가 있습니다.  
  
-   호출 하 여 상태 표시줄을 업데이트를 금지는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.FreezeOutput%2A> 메서드가 있습니다.  
  
-   호출 하 여 상태 표시줄에서 텍스트를 읽고는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.GetText%2A> 메서드 및 메시지 상자에 표시 됩니다.  
  
-   호출 하 여 상태 표시줄 업데이트 허용 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.FreezeOutput%2A> 매개 변수에 0을 전달 하 고 있습니다.  
  
-   호출 하 여 상태 표시줄 내용을 지웁니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.Clear%2A> 방법입니다.  
  
## 참고 항목  
 [상태 표시줄을 확장합니다.](../extensibility/extending-the-status-bar.md)   
 [방법: 상태 표시줄의 진행률 표시줄 영역 프로그래밍](../misc/how-to-program-the-progress-bar-region-of-the-status-bar.md)   
 [방법: 상태 표시줄의 애니메이션 영역 사용](../misc/how-to-use-the-animation-region-of-the-status-bar.md)   
 [방법: 상태 표시줄의 디자이너 영역 프로그래밍](../misc/how-to-program-the-designer-region-of-the-status-bar.md)