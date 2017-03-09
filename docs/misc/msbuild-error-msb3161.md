---
title: "MSBuild 오류 MSB3161 | Microsoft Docs"
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
  - "MSBuild.GenerateBootstrapper.CircularDependency"
helpviewer_keywords: 
  - "MSB3161"
ms.assetid: 2871d071-7c3a-4103-8b14-6ee56564a7f7
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3161
**MSB3161: 빌드된 다음 패키지 사이에 순환 종속성이 발견되었습니다. '\<package\>'**  
  
 이 경고는 부트스트래퍼 패키지 종속성의 그래프에 순환 종속성\(예: A→B→C→A\)이 있는 경우 발생합니다.  이 경우 부트스트래퍼는 어떤 패키지를 먼저 설치할지 결정할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   부트스트래퍼 패키지 파일에서 설명하고 있는 종속성을 변경하거나 상호 종속된 패키지 중 하나를 설치 취소하여 순환 종속성을 제거합니다.  
  
## 참고 항목  
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)   
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)