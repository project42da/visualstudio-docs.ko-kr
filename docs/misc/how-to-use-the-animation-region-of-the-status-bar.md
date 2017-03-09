---
title: "방법: 상태 표시줄의 애니메이션 영역 사용 | Microsoft Docs"
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
  - "상태 표시줄, 프로그래밍"
  - "상태 표시줄, 애니메이션 영역"
  - "애니메이션 영역, 상태 표시줄"
ms.assetid: ec6fb915-7bc8-4a90-8156-70c1a243caff
caps.latest.revision: 14
caps.handback.revision: 14
manager: "douge"
---
# 방법: 상태 표시줄의 애니메이션 영역 사용
애니메이션 영역을 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 오래 또는 결정 되지 않은 길이에 작업 \(예를 들어, 여러 프로젝트는 솔루션의 구축\)을 나타내는 반복 애니메이션 상태 표시줄에 표시 됩니다.  
  
### Visual Studio 상태 표시줄의 애니메이션 영역을 사용 하려면  
  
1.  인스턴스를 가져오기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar> 인터페이스를 통해 사용할 수 있게 되는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> 서비스 합니다.  
  
2.  호출 하 여 애니메이션 시작은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.Animation%2A> 메서드는 상태 표시줄의.  1에는 첫 번째 매개 변수 및 두 번째 매개 변수의 값으로 애니메이션된 아이콘에 대 한 참조를 값으로 전달 합니다.  
  
3.  호출 하 여 애니메이션을 중지를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.Animation%2A> 메서드는 상태 표시줄의.  애니메이션된 아이콘 두 번째 매개 변수의 값에 대 한 참조 및 첫 번째 매개 변수의 값에 0을 전달 합니다.  
  
## 예제  
 이 예제에서는 기본 제공 애니메이션 애니메이션 영역을 실행 하는 방법을 보여 줍니다.  
  
 [!CODE [VSSDKAnimationStatusBar#1](../CodeSnippet/VS_Snippets_VSSDK/vssdkanimationstatusbar#1)]  
  
## 참고 항목  
 [상태 표시줄을 확장합니다.](../extensibility/extending-the-status-bar.md)   
 [방법: 상태 표시줄의 피드백 영역에서 읽기 및 피드백 영역에 쓰기](../misc/how-to-read-from-and-write-to-the-feedback-region-of-the-status-bar.md)   
 [방법: 상태 표시줄의 진행률 표시줄 영역 프로그래밍](../misc/how-to-program-the-progress-bar-region-of-the-status-bar.md)   
 [방법: 상태 표시줄의 디자이너 영역 프로그래밍](../misc/how-to-program-the-designer-region-of-the-status-bar.md)