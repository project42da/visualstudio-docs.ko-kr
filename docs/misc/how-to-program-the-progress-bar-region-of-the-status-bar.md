---
title: "방법: 상태 표시줄의 진행률 표시줄 영역 프로그래밍 | Microsoft Docs"
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
  - "상태 표시줄, 진행률 표시줄 영역"
  - "진행률 표시줄, 상태 표시줄"
  - "상태 표시줄, 프로그래밍"
ms.assetid: 4b54616a-8c20-436d-b764-f2380e5760f2
caps.latest.revision: 11
caps.handback.revision: 11
manager: "douge"
---
# 방법: 상태 표시줄의 진행률 표시줄 영역 프로그래밍
진행률 표시줄 영역에 있는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 증분 디스크에 파일을 저장할 빠른 작업 진행 상황, 예를 들어, 상태 표시줄에 표시 됩니다.  
  
### Visual Studio 상태 표시줄의 진행률 표시줄 영역을 사용.  
  
1.  인스턴스를 가져오기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar> 인터페이스를 통해 사용할 수 있게 되는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> 서비스 합니다.  
  
2.  초기화를 호출 하 여 시작 하는 값에는 진행률 표시줄의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.Progress%2A> 메서드.  
  
3.  작업을 사용 하 여 진행 되는 동안 진행률 표시줄을 업데이트는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.Progress%2A> 새 값을 설정 하는 방법입니다.  
  
## 예제  
 이 예제에서는 초기화 하 고 진행률 표시줄을 업데이트 하는 방법을 보여 줍니다.  
  
 [!CODE [VSSDKProgressStatusBar#1](../CodeSnippet/VS_Snippets_VSSDK/vssdkprogressstatusbar#1)]  
  
 예의 코드:  
  
-   인스턴스를 가져옵니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar> 의 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> 서비스.  
  
-   진행률 표시줄을 호출 하 여 시작 값을 지정 된 초기화는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.Progress%2A> 메서드가 있습니다.  
  
-   작업을 반복 하 여 시뮬레이션을 `for` 반복 하 고 진행률 표시줄 값을 사용 하 여 업데이트를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.Progress%2A> 메서드.  
  
-   진행률 표시줄을 사용 하 여 취소는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.Clear%2A> 메서드.  
  
## 참고 항목  
 [상태 표시줄을 확장합니다.](../extensibility/extending-the-status-bar.md)   
 [방법: 상태 표시줄의 피드백 영역에서 읽기 및 피드백 영역에 쓰기](../misc/how-to-read-from-and-write-to-the-feedback-region-of-the-status-bar.md)   
 [방법: 상태 표시줄의 애니메이션 영역 사용](../misc/how-to-use-the-animation-region-of-the-status-bar.md)   
 [방법: 상태 표시줄의 디자이너 영역 프로그래밍](../misc/how-to-program-the-designer-region-of-the-status-bar.md)