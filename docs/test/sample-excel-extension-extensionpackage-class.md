---
title: "샘플 Excel 확장: ExtensionPackage 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6e45410a-1819-4d54-ac21-7280152f7e3a
caps.latest.revision: 9
ms.author: "mlearned"
manager: "douge"
caps.handback.revision: 9
---
# 샘플 Excel 확장: ExtensionPackage 클래스
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 클래스는 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage> 클래스를 확장하며, [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] 워크시트를 테스트하는 코딩된 UI 테스트의 진입점을 제공합니다.  
  
## 어셈블리 특성  
 이 파일은 어셈블리를 UI 테스트 확장으로 식별하는 어셈블리 특성으로 시작합니다.  
  
```  
[assembly: Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage(  
    "ExcelExtensionPackage",  
    typeof(  
     Microsoft.VisualStudio.Test.Sample.UI.ExtensionPackage))]  
```  
  
 이 특성은 기본 클래스 이름, 패키지 클래스 이름 및 사용자 지정 확장 패키지 클래스의 정규화된 클래스 이름을 선언합니다.  
  
## 단순 속성  
 이 클래스에는 코딩된 UI 테스트 프레임워크에서 확장 및 어셈블리를 식별하고 설명하는 데 사용되는 값을 제공하는 속성이 있습니다.  자세한 내용은 코드 주석을 참조하십시오.  
  
## GetService 메서드  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage.GetService%2A> 메서드는 코딩된 UI 테스트 프레임워크에서 각 개체의 기본 클래스로 식별된 기술 관리자, 속성 공급자 및 작업 필터에 액세스하는 데 사용되는 단일 진입점입니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>   
 [Microsoft Excel을 지원하도록 코딩된 UI 테스트 및 작업 기록 확장](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)