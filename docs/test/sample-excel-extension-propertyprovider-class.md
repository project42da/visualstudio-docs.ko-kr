---
title: "샘플 Excel 확장: PropertyProvider 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 075d9b8d-8658-4fca-8711-08304dbac1c5
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "mlearned"
manager: "douge"
---
# 샘플 Excel 확장: PropertyProvider 클래스
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 내부 클래스는 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider> 클래스를 확장하며 [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] 요소에서 UI\(사용자 인터페이스\) 테스트를 기록하고 재생하기 위한 속성 서비스를 제공합니다.  
  
## GetControlSupportLevel 메서드  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider.GetControlSupportLevel%2A> 메서드는 속성 공급자가 지정된 컨트롤에 대해 제공할 수 있는 지원 수준을 나타내는 숫자를 반환합니다.  반환되는 값이 높을수록 속성 공급자가 해당 컨트롤을 지원할 수 있는 수준이 높습니다.  이 경우 메서드는 지정된 컨트롤의 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IUITechnologyElement.TechnologyName%2A> 속성 값을 확인합니다.  이 값이 "Excel"이고 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IUITechnologyElement.ControlTypeName%2A>이 해당 컨트롤이 `CellElement`임을 나타내는 경우 이 메서드는 가장 높은 값을 반환하고, 그렇지 않으면 지원이 제공되지 않음을 나타내는 0을 반환합니다.  
  
## GetPropertyNames 메서드  
 Excel Cell 컨트롤의 지원되는 속성에 대한 속성 이름 및 속성 설명으로 구성된 사전을 반환합니다.  
  
## GetPropertyDescriptor 메서드  
 테스트 프레임워크에서는 이 메서드를 호출하여 제공된 속성 이름에 대한 미리 정의된 속성 설명을 가져옵니다.  
  
## GetPropertyValue 및 SetPropertyValue 메서드  
 `GetPropertyValue` 메서드는 이 확장의 `Communicator` 클래스를 사용하여 Excel에서 속성 값을 반환합니다.  `SetPropertyValue` 메서드는 <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard> 클래스와 `Communicator` 구성 요소를 사용하여 속성 값을 설정합니다.  이러한 메서드는 테스트 프레임워크에 의해 호출됩니다.  
  
## 코드 생성 사용자 지정 메서드  
 이러한 메서드는 이 확장에 대해 구현되지 않았습니다.  따라서 이러한 메서드는 `null`을 반환하거나 <xref:System.NotImplementedException>을 throw합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>   
 <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard>   
 [Microsoft Excel을 지원하도록 코딩된 UI 테스트 및 작업 기록 확장](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)