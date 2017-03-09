---
title: "MSBuild 오류 MSB3141 | Microsoft Docs"
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
  - "MSBuild.GenerateBootstrapper.MissingVerificationInformation"
  - "vsdeploy.chm:13141"
helpviewer_keywords: 
  - "MSB3141"
ms.assetid: f32ce5fd-bb82-4a8b-aebe-61efef89cdc1
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3141
**MSB3141: '\<package\>' 항목의 '\<file\>' 파일에 'PublicKey' 또는 'Hash' 특성을 지정하지 않았습니다.**  
  
 이 오류는 부트스트래퍼 패키지에 대해 HomeSite를 사용하려 할 때 발생합니다.  그러나 런타임에 부트스트래퍼 매니페스트에는 파일 확인을 위한 올바른 정보\(공개 키 또는 해시\)가 들어 있지 않습니다.  
  
### 이 오류를 해결하려면  
  
-   부족한 정보가 들어 있는 패키지 파일을 다운로드하여 부트스트래퍼 캐시에 복사합니다.  
  
## 참고 항목  
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)