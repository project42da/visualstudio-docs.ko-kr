---
title: "MSBuild 오류 MSB3153 | Microsoft Docs"
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
  - "MSBuild.GenerateBootstrapper.PackageValidation"
helpviewer_keywords: 
  - "MSB3153"
ms.assetid: 937bb1ff-79f7-45a5-a085-525f4b48ea4e
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3153
**MSB3153: '\<folder\>'에 있는 '\<package\>' 항목에 대한 XML 유효성 검사가 실패했습니다.**  
  
 이 경고는 매니페스트\(특히 package.xml\)가 XML 유효성 검사를 통과하지 못한 경우 발생합니다.  이어지는 오류 메시지에는 구체적인 문제가 표시됩니다\([MSBuild 오류 MSB3159](../misc/msbuild-error-msb3159.md) 또는 [MSBuild 오류 MSB3160](../misc/msbuild-error-msb3160.md)\).  
  
### 이 오류를 해결하려면  
  
-   이어지는 오류 메시지에 표시된 매니페스트 유효성 검사 문제를 해결합니다.  
  
## 참고 항목  
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)   
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)