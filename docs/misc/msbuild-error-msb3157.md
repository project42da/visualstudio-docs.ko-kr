---
title: "MSBuild 오류 MSB3157 | Microsoft Docs"
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
  - "vsdeploy.chm:13157"
  - "MSBuild.GenerateBootstrapper.UsingProductCulture"
helpviewer_keywords: 
  - "MSB3157"
ms.assetid: ccfcbea4-eb9b-42ae-9908-47079ecc84a7
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3157
**MSB3157: '\<package\>' 항목에 대해 일치하는 '\<culture\>' culture가 없습니다.  '\<culture\>' culture를 대신 사용합니다.**  
  
 이 경고는 지정된 culture를 사용하는 패키지 매니페스트 파일\(package.xml\)을 지정된 제품이 찾을 수 없는 경우 발생합니다.  
  
### 이 오류를 해결하려면  
  
-   적절한 패키지 매니페스트 파일을 제공합니다.  
  
## 참고 항목  
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)