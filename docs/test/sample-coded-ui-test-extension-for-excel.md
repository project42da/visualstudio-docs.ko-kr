---
title: "Excel용 샘플 코딩된 UI 테스트 확장 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "코딩된 UI 테스트, Excel용 확장"
ms.assetid: 451e4d14-7fac-42f9-af56-2bdc8414c6c7
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "mlearned"
manager: "douge"
---
# Excel용 샘플 코딩된 UI 테스트 확장
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 샘플의 확장 구성 요소는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 코딩된 UI 테스트 프로세스에서 실행되며, `ExtensionPackage` 클래스를 기본 클래스로 하는 다소 계층적인 구성 요소입니다.  컨트롤 요소가 최상위 수준에 있고 그 다음 수준에는 `TechnologyManager`, `ActionFilter` 및 `PropertyProvider` 클래스가 있습니다.  
  
 ![Excel 테스트 확장 아키텍처](../test/media/excel_extarch.png "Excel\_ExtArch")  
Excel 확장 아키텍처  
  
## 확장 지점  
 다음 클래스는 [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)]용 코딩된 UI 테스트를 사용할 수 있도록 샘플에서 구현되는 확장 지점을 나타냅니다.  
  
### ExtensionPackage  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage> 클래스에서 상속되며, 코딩된 UI 테스트 확장의 진입점입니다.  이 추상 클래스를 구현하면 코딩된 UI 테스트 프레임워크에서 새 UI를 테스트하기 위해 사용자 지정 UI 테스트 기술 관리자, UI 테스트 속성 공급자 및 UI 테스트 작업 필터에 내부적으로 액세스할 수 있습니다.  자세한 내용은 [ExtensionPackage 클래스](../test/sample-excel-extension-extensionpackage-class.md)을 참조하십시오.  
  
### TechnologyManager  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager> 클래스에서 상속되며, 테스트 기록 및 재생을 위한 기술 관리자를 제공합니다.  자세한 내용은 [TechnologyManager 클래스](../test/sample-excel-extension-technologymanager-class.md)을 참조하십시오.  
  
### ActionFilter  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> 클래스에서 상속되며, 비슷한 테스트 작업 결과를 단일 테스트 결과로 집계하기 위한 기본 클래스를 제공합니다.  자세한 내용은 [ActionFilter 클래스](../test/sample-excel-extension-actionfilter-class.md)을 참조하십시오.  
  
### 기술 요소  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement> 클래스에서 상속된 기본 클래스는 기록 및 재생 가능한 UI 테스트의 기술 요소를 위한 기초를 제공합니다.  자세한 내용은 [요소 클래스](../test/sample-excel-extension-element-classes.md)을 참조하십시오.  
  
### PropertyProvider  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider> 클래스에서 상속되며, 테스트 기록 및 재생에 사용되는 UI 요소의 속성을 지원하기 위한 기본 클래스를 제공합니다.  자세한 내용은 [PropertyProvider 클래스](../test/sample-excel-extension-propertyprovider-class.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>   
 [ExtensionPackage 클래스](../test/sample-excel-extension-extensionpackage-class.md)   
 [TechnologyManager 클래스](../test/sample-excel-extension-technologymanager-class.md)   
 [ActionFilter 클래스](../test/sample-excel-extension-actionfilter-class.md)   
 [요소 클래스](../test/sample-excel-extension-element-classes.md)   
 [PropertyProvider 클래스](../test/sample-excel-extension-propertyprovider-class.md)