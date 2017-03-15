---
title: "MSBuild 오류 MSB3164 | Microsoft Docs"
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
  - "MSBuild.GenerateBootstrapper.PackageHomeSiteMissing"
helpviewer_keywords: 
  - "MSB3164"
ms.assetid: 5a1e31fc-0322-4d4e-8c26-013b1efb82c9
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3164
**MSB3164: '\<package\>'에 대해 'HomeSite' 특성을 지정하지 않았으므로 부트스트래퍼와 같은 위치에 패키지가 게시됩니다.**  
  
 이 경고는 사용자가 HomeSite를 사용하려 하지만 지정된 패키지에 대한 적절한 HomeSite 정보를 사용할 수 없는 경우 발생합니다.  
  
### 이 오류를 해결하려면  
  
-   HomeSite 정보가 포함되도록 매니페스트 파일을 업데이트합니다.  
  
-   또는 HomeSite를 사용하지 않을 수도 있습니다.  
  
## 참고 항목  
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)