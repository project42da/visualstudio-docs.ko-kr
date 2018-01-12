---
title: "방법: SharePoint 솔루션에 대 한 사용자 지정 기능 및 패키지 유효성 검사 규칙 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending deployment
- SharePoint development in Visual Studio, validation rules
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: efc9cc2988125621212698576deeca1247e26a58
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions"></a>방법: SharePoint 솔루션에 대한 사용자 지정 기능 및 패키지 유효성 검사 규칙 만들기
  Visual Studio에서 생성 하는 솔루션 패키지를 확인 하기 위한 사용자 지정 유효성 검사 규칙을 만들 수 있습니다. 선택 하 여 전체 기능 또는 패키지에서 전체 유효성 검사를 수행할 수 있습니다 **유효성 검사** 패키지 또는 기능에의 상황에 맞는 메뉴는 **PackagingExplorer**합니다. 부분 유효성 검사는 경우 패키지 또는 기능 것에 유효한 상태를 확인 하는 프로젝트에 새 SharePonit 프로젝트 항목 또는 기능을 추가할 때 수행 됩니다.  
  
### <a name="to-create-a-custom-package-validation-rule"></a>사용자 지정 패키지 유효성 검사 규칙을 만들려면  
  
1.  클래스 라이브러리 프로젝트를 만듭니다.  
  
2.  다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   System.ComponentModel.Composition  
  
3.  다음 인터페이스 중 하나를 구현 하는 클래스를 만듭니다.  
  
    -   패키지 유효성 검사 규칙을 만들려면 구현에서 <xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule> 인터페이스입니다.  
  
    -   기능 유효성 검사 규칙을 만들려면 구현에서 <xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule> 인터페이스입니다.  
  
4.  추가 된 <xref:System.ComponentModel.Composition.ExportAttribute> 클래스에 있습니다. 이 특성을 사용 하면 Visual Studio를 검색 하 고 유효성 검사 규칙을 로드 합니다. 전달 된 <xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule> 또는 <xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule> 형식을 특성 생성자에 있습니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 사용자 지정 기능 유효성 검사 규칙을 만드는 방법을 보여 줍니다.  
  
 [!code-vb[SPExtensibility.FeatureValidation#1](../sharepoint/codesnippet/VisualBasic/featurevalidation/extension/customvalidationrule.vb#1)]
 [!code-csharp[SPExtensibility.FeatureValidation#1](../sharepoint/codesnippet/CSharp/featurevalidation/extension/customfeaturevalidationrule.cs#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 어셈블리에 대 한 참조가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint 합니다.  
  
-   System.ComponentModel.Composition 합니다.  
  
## <a name="deploying-the-extension"></a>확장 배포  
 확장을 배포 하려면 만듭니다는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 어셈블리 및 확장과 함께 하려는 다른 파일에 대 한 패키지 (VSIX) 확장 합니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구에 대 한 확장명 배포](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 패키징 및 배포 확장](../sharepoint/extending-sharepoint-packaging-and-deployment.md)  
  
  