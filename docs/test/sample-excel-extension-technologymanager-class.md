---
title: "샘플 Excel 확장: TechnologyManager 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8a7b760d-b5ac-4451-9593-6ac1a0b95cdb
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "mlearned"
manager: "douge"
---
# 샘플 Excel 확장: TechnologyManager 클래스
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 클래스는 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager> 클래스를 확장하며 [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] 확장을 위한 핵심 서비스를 제공합니다.  기본 클래스에는 여러 메서드가 있지만 이 샘플에서는 그 중 일부만 사용됩니다.  
  
 일부 메서드는 단지 속성 값을 반환하기만 하지만  대부분의 메서드는 개발자가 기본 알고리즘 빌드를 코딩된 UI 테스트 엔진으로 재정의하는 데 사용할 수 있습니다.  이러한 메서드는 <xref:System.NotSupportedException>을 throw하거나 프레임워크가 기본 알고리즘을 사용하도록 지정하는 `null`을 반환합니다.  
  
 기술 관리자 코드를 개발하는 데는 기본 기술의 복잡성에 따라 몇 주에서 몇 달까지 소요될 수 있습니다.  Excel을 사용하면 잠재적으로 매우 광범위한 기술 관리자를 만들 수 있습니다.  이 예제는 의도적으로 Excel 워크시트 및 셀로 제한되어 있으며 제한된 형식을 사용합니다.  
  
 가능한 경우 기술 관리자 코드는 `Communicator` 클래스에 의해 열린 .NET Remoting 채널을 사용하여 Excel 프로세스에서 실행 중인 추가 기능에서 정보를 추출합니다.  
  
## COM 노출 여부  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement> 클래스를 확장하는 각 요소 클래스와 이 클래스 모두에는 클래스가 COM에 노출되도록 `true` 값으로 설정된 <xref:System.Runtime.InteropServices.ComVisibleAttribute>가 있습니다.  
  
## TechnologyName 속성  
 이 속성은 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.TechnologyName%2A?displayProperty=fullName> 속성이 재정의된 것으로, 확장의 다른 모든 구성 요소에 기본 기술을 식별하는 고유하고 의미 있는 이름을 제공해야 합니다.  이 확장의 경우 값은 "Excel"입니다.  
  
## GetControlSupportLevel 메서드  
 이 메서드는 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.GetControlSupportLevel%2A?displayProperty=fullName> 메서드가 재정의된 것으로, 지정된 핸들이 나타내는 컨트롤에 대해 기술 관리자가 제공할 수 있는 지원 수준을 나타내는 숫자를 반환합니다.  반환되는 값이 높을수록 기술 관리자가 해당 컨트롤을 지원할 수 있는 수준이 높습니다.  이 경우 이 메서드는 컨트롤이 포함된 창을 검사하여 이 창이 Excel 워크시트이면 가장 높은 값을 반환하고, 그렇지 않으면 지원이 제공되지 않음을 나타내는 0을 반환합니다.  
  
## 요소를 가져오는 메서드  
 코딩된 UI 테스트 프레임워크에서 핸들, 화면의 지점 또는 다른 기술의 요소를 제공하여 기술과 관련된 요소를 가져오는 데 사용되는 몇 가지 중요한 메서드가 있습니다.  이러한 메서드의 코드는 코드만으로도 어떤 코드인지 어느 정도 이해할 수 있습니다.  기본 메서드는 다음과 같습니다.  
  
-   <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.GetFocusedElement%2A?displayProperty=fullName>  
  
-   <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.GetElementFromPoint%2A?displayProperty=fullName>  
  
-   <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.GetElementFromWindowHandle%2A?displayProperty=fullName>  
  
-   <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.GetElementFromNativeElement%2A?displayProperty=fullName>  
  
-   <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.ConvertToThisTechnology%2A?displayProperty=fullName>  
  
## ParseQueryId 메서드  
 코딩된 UI 테스트를 만든 경우 사용자가 테스트의 일부 또는 모든 컨트롤에 대한 속성 값을 지정할 수 있습니다.  테스트 프레임워크에서는 이러한 속성 값을 사용하여 테스트 중 특정 UI 컨트롤을 찾는 데 사용되는 검색 속성이라는 이름\-값 쌍을 만듭니다.  모든 검색 속성은 모든 컨트롤을 포함하는 기술에서 모든 요소의 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.QueryId%2A?displayProperty=fullName> 속성 값을 나타냅니다.  테스트 중 컨트롤을 여러 번 찾아야 할 수 있으므로 이 메서드를 통해 기술 관리자는 지정된 컨트롤의 검색 속성에 대한 구문 분석을 최적화할 수 있습니다.  이 메서드는 프레임워크에서 해당 컨트롤의 후속 검색에 사용할 수 있는 쿠키도 반환합니다.  이 메서드 구현에서는 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.AndCondition.Match%2A?displayProperty=fullName> 메서드를 사용하여 검색 속성을 구문 분석합니다.  
  
## MatchElement 메서드  
 기술 관리자를 통해 컨트롤 검색을 수행하려면 가능한 일치 항목의 배열을 반환하거나 프레임워크에서 고유한 검색 알고리즘을 사용하도록 지정하는 <xref:System.NotSupportedException>을 throw하도록 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.Search%2A?displayProperty=fullName> 메서드를 구현합니다.  어떤 방법을 사용하든 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.MatchElement%2A> 메서드를 구현해야 합니다. 이 구현에는 다시 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.AndCondition.Match%2A?displayProperty=fullName> 메서드가 사용됩니다.  
  
## 탐색 메서드  
 이러한 메서드는 UI 계층 구조에서 지정된 요소의 부모, 자식 또는 형제를 가져옵니다.  이 코드는 간단하고 명확하게 주석 처리되어 있습니다.  
  
## GetExcelElement 내부 메서드  
 이 내부 메서드는 Excel 요소에 대한 창 핸들 및 정보를 가져오고, 요청된 Excel 요소를 반환합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager>   
 <xref:System.NotSupportedException>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>   
 <xref:System.Runtime.InteropServices.ComVisibleAttribute>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.QueryId%2A>   
 [Microsoft Excel을 지원하도록 코딩된 UI 테스트 및 작업 기록 확장](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)