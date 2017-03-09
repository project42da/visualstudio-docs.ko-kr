---
title: "MSBuild 오류 MSB3165 | Microsoft Docs"
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
  - "vsdeploy.chm:13165"
  - "MSBuild.GenerateBootstrapper.DifferingPublicKeys"
helpviewer_keywords: 
  - "MSB3165"
ms.assetid: 2f50462e-947d-4211-b197-e58eddcfd373
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3165
**MSB3165: '\<package\>'의 '\<public key\>' 특성 값이 '\<file\>' 파일의 해당 값과 일치하지 않습니다.**  
  
 이 경고는 부트스트래퍼 패키지 파일에 지정된 공개 키가 디스크에 있는 재배포 가능 패키지의 시그니처와 일치하지 않거나 재배포 가능 패키지가 서명되지 않은 경우 발생합니다.  이 패키지를 서명한 경우 빌드에는 디스크에 있는 해당 패키지의 공개 키가 사용되고, 서명하지 않은 경우에는 디스크에 있는 재배포 가능 패키지의 해시가 사용됩니다.  
  
## 참고 항목  
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)   
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)