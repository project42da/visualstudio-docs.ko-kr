---
title: "&lt;RelatedProducts&gt; 요소(부트스트래퍼) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateBootstrapper.MissingDependency"
  - "MSBuild.GenerateBootstrapper.DuplicateItems"
  - "MSBuild.GenerateBootstrapper.IncludedProductIncluded"
  - "MSBuild.GenerateBootstrapper.DependencyNotFound"
  - "MSBuild.GenerateBootstrapper.PackageFileNotFound"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "<RelatedProducts> 요소[부트스트래퍼]"
ms.assetid: bf152712-4c1e-48bd-9b7f-311cf0fdb832
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;RelatedProducts&gt; 요소(부트스트래퍼)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`RelatedProducts` 요소는 현재 제품에 포함되거나 종속되는 다른 제품을 정의합니다.  
  
## 구문  
  
```  
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
  
## 요소 및 특성  
 `RelatedProducts` 요소는 `Product` 요소의 자식입니다.  특성이 없습니다.  
  
## DependsOnProduct  
 `DependsOnProduct` 요소는 현재 제품이 명명된 제품에 종속되어 있으며 현재 제품을 설치하기 전에 명명된 제품을 설치하도록 지정합니다.  이 요소는 `RelatedProducts` 요소의 자식입니다.  `RelatedProducts` 요소에는 `DependsOnProduct` 요소가 하나 이상 있을 수 있습니다.  
  
 `DependsOnProduct`에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Code`|`Product` 요소의 `ProductCode` 특성에서 지정한 포함된 제품의 코드 이름입니다.  자세한 내용은 [\<Product\> 요소](../deployment/product-element-bootstrapper.md)를 참조하십시오.|  
  
## EitherProducts  
 `EitherProducts` 요소는 0개 이상의 `DependsOnProduct` 요소를 정의하고 특성을 가지고 있지 않습니다.  현재 제품을 설치하기 전에 이 집합에 있는 하나 이상의 `DependsOnProduct`를 설치해야 합니다.  `RelatedProducts` 요소에는 `EitherProducts` 요소가 0개 이상 있을 수 있습니다.  
  
## IncludesProduct  
 `IncludesProduct` 요소는 제품이 현재 설치 항목에 포함되어 있으며 별도의 설치가 필요하지 않음을 나타냅니다.  이 요소는 `RelatedProducts` 요소의 자식입니다.  `RelatedProducts` 요소에는 `IncludesProduct` 요소가 하나 이상 있을 수 있습니다.  
  
 `IncludesProduct`에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Code`|`Product` 요소의 `ProductCode` 특성에서 지정한 포함된 제품의 코드 이름입니다.  자세한 내용은 [\<Product\> 요소](../deployment/product-element-bootstrapper.md)를 참조하십시오.|  
  
## 예제  
 다음 코드 예제에서는 Microsoft Installer를 별도의 설치 작업 없이 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]와 함께 설치하도록 지정합니다.  
  
```  
<RelatedProducts>  
    <IncludesProduct Code="Microsoft.Windows.Installer.2.0" />  
</RelatedProducts>  
```  
  
## 참고 항목  
 [\<Product\> 요소](../deployment/product-element-bootstrapper.md)