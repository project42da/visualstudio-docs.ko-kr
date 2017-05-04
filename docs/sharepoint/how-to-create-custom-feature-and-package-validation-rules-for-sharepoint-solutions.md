---
title: "How to: Create Custom Feature and Package Validation Rules for SharePoint Solutions | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "SharePoint development in Visual Studio, extending deployment"
  - "SharePoint development in Visual Studio, validation rules"
ms.assetid: 17e818f8-0f3a-4a96-a6fc-1634ddb4825d
caps.latest.revision: 18
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# How to: Create Custom Feature and Package Validation Rules for SharePoint Solutions
  사용자 지정 유효성 검사 규칙을 만들어 Visual Studio에서 생성된 솔루션 패키지를 확인할 수 있습니다.  **패키징탐색기**에 있는 패키지나 기능의 상황에 맞는 메뉴에서 **유효성 검사**를 선택하여 전체 기능 또는 패키지에 대해 모든 유효성 검사를 수행할 수 있습니다.  프로젝트에 새 SharePonit 프로젝트 항목이나 기능을 추가하는 경우에는 부분 유효성 검사를 수행하여 패키지나 기능이 유효한 상태에 있는지 확인할 수 있습니다.  
  
### 사용자 지정 패키지 유효성 검사 규칙을 만들려면  
  
1.  클래스 라이브러리 프로젝트를 만듭니다.  
  
2.  다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   System.ComponentModel.Composition  
  
3.  다음 인터페이스 중 하나를 구현하는 클래스를 만듭니다.  
  
    -   패키지 유효성 검사 규칙을 만들려면 <xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule> 인터페이스를 구현합니다.  
  
    -   기능 유효성 검사 규칙을 만들려면 <xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule> 인터페이스를 구현합니다.  
  
4.  클래스에 <xref:System.ComponentModel.Composition.ExportAttribute>를 추가합니다.  이 특성을 사용하면 Visual Studio에서 유효성 검사 규칙을 찾아 로드할 수 있습니다.  <xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule> 또는 <xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule> 형식을 특성 생성자에 전달합니다.  
  
## 예제  
 다음 코드 예제에서는 사용자 지정 기능 유효성 검사 규칙을 만드는 방법을 보여 줍니다.  
  
 [!code-csharp[SPExtensibility.FeatureValidation#1](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.featurevalidation/cs/extension/customfeaturevalidationrule.cs#1)]
 [!code-vb[SPExtensibility.FeatureValidation#1](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.featurevalidation/vb/extension/customvalidationrule.vb#1)]  
  
## 코드 컴파일  
 이 예제에는 다음 어셈블리에 대한 참조가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## 확장 배포  
 확장을 배포하려면 어셈블리 및 확장과 함께 배포할 다른 모든 파일에 대한 VSIX\([!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Extension\) 패키지를 만듭니다.  자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)를 참조하십시오.  
  
## 참고 항목  
 [Extending SharePoint Packaging and Deployment](../sharepoint/extending-sharepoint-packaging-and-deployment.md)  
  
  