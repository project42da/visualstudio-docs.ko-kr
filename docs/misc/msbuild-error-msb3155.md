---
title: "MSBuild 오류 MSB3155 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateBootstrapper.ProductNotFound"
helpviewer_keywords: 
  - "MSB3155"
ms.assetid: 59bf2293-ef13-4bb1-8f29-5d6966bbe313
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3155
**MSBuild 오류 MSB3155: '\<path\>'에서 '\<package\>' 항목을 찾을 수 없습니다.**  
  
 이 경고는 <xref:Microsoft.Build.Tasks.Deployment.Bootstrapper.Product.ProductCode%2A>가 지정된 패키지를 부트스트래퍼 캐시에서 찾을 수 없는 경우 발생합니다.  
  
> [!NOTE]
>  MDAC\(Microsoft Data Access Components\)는 더 이상 부트스트래퍼 패키지로 포함되지 않으며  [Microsoft Windows Update](http://go.microsoft.com/fwlink/?LinkId=86676) 웹 사이트에서 다운로드할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   설치할 패키지 목록에서 패키지를 제거하거나 패키지를 캐시에 추가합니다.  매니페스트가 유효한 XML 태그를 사용하여 올바른 형식으로 작성되었는지도 확인합니다.  
  
## 참고 항목  
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)   
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)   
 [필수 조건 대화 상자](../ide/reference/prerequisites-dialog-box.md)   
 [부트스트래퍼 패키지 만들기](../deployment/creating-bootstrapper-packages.md)