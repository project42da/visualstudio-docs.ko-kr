---
title: "샘플 Excel 확장: ActionFilter 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c69fe3c7-f797-4e90-b21c-f2cc4dddf152
caps.latest.revision: 11
ms.author: "mlearned"
manager: "douge"
caps.handback.revision: 11
---
# 샘플 Excel 확장: ActionFilter 클래스
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 내부 클래스는 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> 클래스를 확장하며 [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] 요소의 테스트 작업에 대한 필터를 나타냅니다.  
  
## 단순 속성  
 개발자는 이러한 읽기 전용 속성을 사용하여 코딩된 UI 테스트 프레임워크에서 이 테스트 작업 필터를 실행할 방법을 지정할 수 있습니다.  예를 들어 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Name%2A> 속성은 작업 필터의 이름을 제공합니다.  다른 속성은 작업 필터의 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Category%2A>와 이 테스트 작업 필터를 통해 필터링되는 테스트 작업의 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.FilterType%2A> 및 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Group%2A> 이름을 가져옵니다.  또한 일부 속성은 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.ApplyTimeout%2A> 여부 및 테스트 작업의 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Enabled%2A> 여부를 나타냅니다.  
  
## ProcessRule 메서드  
 이 메서드는 코딩된 UI 테스트 프레임워크에서 호출되며 지정된 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>에 대한 필터를 실행합니다.  이 특정 재정의 마우스 제거 스택의 다음 동작 셀에 키 입력을 보내면 작업의 셀을 선택 합니다.  그런 다음 `false`를 반환합니다.  
  
## Private 메서드  
 `IsLeftClick` 메서드는 지정된 작업이 마우스 왼쪽 클릭을 나타내는지 여부를 확인합니다.  `AreActionsOnSameExcelCell` 메서드는 지정된 두 작업이 Excel의 동일한 셀에서 실행되는지 여부를 확인합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>   
 [Microsoft Excel을 지원하도록 코딩된 UI 테스트 및 작업 기록 확장](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)