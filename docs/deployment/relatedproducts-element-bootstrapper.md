---
title: '&lt;RelatedProducts&gt; 요소 (부트스트래퍼) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- MSBuild.GenerateBootstrapper.MissingDependency
- MSBuild.GenerateBootstrapper.DuplicateItems
- MSBuild.GenerateBootstrapper.IncludedProductIncluded
- MSBuild.GenerateBootstrapper.DependencyNotFound
- MSBuild.GenerateBootstrapper.PackageFileNotFound
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- <RelatedProducts> element [bootstrapper]
ms.assetid: bf152712-4c1e-48bd-9b7f-311cf0fdb832
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5701b88f3942301c8fdb6d674fc323e62a93589b
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815459"
---
# <a name="ltrelatedproductsgt-element-bootstrapper"></a>&lt;RelatedProducts&gt; 요소 (부트스트래퍼)
`RelatedProducts` 요소에 종속 되거나 현재 제품에 포함 된 다른 제품을 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<RelatedProducts>  
    <DependsOnProduct  
        Code  
    />  
    <EitherProducts>  
        <DependsOnProduct  
            Code  
        />  
    </EitherProducts>  
    <IncludesProduct  
        Code  
    />  
</RelatedProducts>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `RelatedProducts` 의 자식인 요소는 `Product` 요소입니다. 특성이 없습니다.  
  
## <a name="dependsonproduct"></a>DependsOnProduct  
 `DependsOnProduct` 요소 의미 현재 전에 명명된 된 제품을 설치 해야 하 고 현재 제품 명명된 된 제품에 따라 달라 집니다. 자식인는 `RelatedProducts` 요소입니다. A `RelatedProducts` 하나 이상 있을 수 있습니다 `DependsOnProduct` 요소입니다.  
  
 `DependsOnProduct` 에 다음 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Code`|에 지정 된 대로 포함된 된 제품의 코드명은 `ProductCode` 의 특성은 `Product` 요소입니다. 자세한 내용은 참조 [ \<제품 > 요소](../deployment/product-element-bootstrapper.md)합니다.|  
  
## <a name="eitherproducts"></a>EitherProducts  
 `EitherProducts` 요소 0 개 이상의 정의 `DependsOnProduct` 요소 특성이 없습니다. 하나 이상의 `DependsOnProduct` 이 집합에는 현재 제품 하기 전에 설치 되어야 해야 합니다. A `RelatedProducts` 요소는 0 또는 그 이상 있을 수 있습니다 `EitherProducts` 요소입니다.  
  
## <a name="includesproduct"></a>IncludesProduct  
 `IncludesProduct` 요소 의미 제품이 현재 설치에 포함 되며 별도 설치는 필요 하지 않습니다. 자식인는 `RelatedProducts` 요소입니다. A `RelatedProducts` 하나 이상 있을 수 있습니다 `IncludesProduct` 요소입니다.  
  
 `IncludesProduct` 에 다음 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Code`|에 지정 된 대로 포함된 된 제품의 코드명은 `ProductCode` 의 특성은 `Product` 요소입니다. 자세한 내용은 참조 [ \<제품 > 요소](../deployment/product-element-bootstrapper.md)합니다.|  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 지정 Microsoft 설치 관리자와 함께 설치 되는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], 별도 설치 필요 하지 것입니다.  
  
```xml  
<RelatedProducts>  
    <IncludesProduct Code="Microsoft.Windows.Installer.2.0" />  
</RelatedProducts>  
```  
  
## <a name="see-also"></a>참고 항목  
 [\<제품 > 요소](../deployment/product-element-bootstrapper.md)