---
title: "방법: 상태 표시줄의 디자이너 영역 프로그래밍 | Microsoft Docs"
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
  - "디자이너 영역, 상태 표시줄"
  - "상태 표시줄, 프로그래밍"
  - "상태 표시줄, 디자이너 영역"
ms.assetid: 735a86bb-80b2-4557-9677-00799856017f
caps.latest.revision: 11
caps.handback.revision: 11
manager: "douge"
---
# 방법: 상태 표시줄의 디자이너 영역 프로그래밍
디자이너 영역에는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 상태 표시줄 편집, 예를 들어, 줄 번호 또는 열 수를 커서 위치에 관련 된 정보를 표시 합니다.  
  
### 디자이너 영역의 Visual Studio 상태 표시줄의 프로그램을  
  
1.  인스턴스를 가져오기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar> 인터페이스를 통해 사용할 수 있게 되는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> 서비스 합니다.  
  
2.  호출 하 여 디자이너 영역 상태 표시줄을 업데이트는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.SetInsMode%2A> 메서드 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.SetLineColChar%2A> 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar> 인스턴스.  
  
## 예제  
 이 예제에서는 상태 표시줄의 디자이너 영역을 프로그래밍 하는 방법을 보여 줍니다.  
  
 [!code-vb[VSSDKDesignerStatusBar#1](../misc/codesnippet/VisualBasic/how-to-program-the-designer-region-of-the-status-bar_1.vb)]
 [!code-cs[VSSDKDesignerStatusBar#1](../misc/codesnippet/CSharp/how-to-program-the-designer-region-of-the-status-bar_1.cs)]  
  
## 참고 항목  
 [상태 표시줄을 확장합니다.](../extensibility/extending-the-status-bar.md)   
 [방법: 상태 표시줄의 피드백 영역에서 읽기 및 피드백 영역에 쓰기](../misc/how-to-read-from-and-write-to-the-feedback-region-of-the-status-bar.md)   
 [방법: 상태 표시줄의 진행률 표시줄 영역 프로그래밍](../misc/how-to-program-the-progress-bar-region-of-the-status-bar.md)   
 [방법: 상태 표시줄의 애니메이션 영역 사용](../misc/how-to-use-the-animation-region-of-the-status-bar.md)